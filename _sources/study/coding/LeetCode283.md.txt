# LeetCode 283 移动零

```python
from typing import List


class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        next_zero_idx = -1

        # 找到下一个0的位置
        for _next_zero_idx in range(len(nums)):
            if nums[_next_zero_idx] == 0:
                next_zero_idx = _next_zero_idx
                break

        # 找到下一个非0的位置
        for idx in range(len(nums)):
            if nums[idx] != 0 and next_zero_idx < idx and next_zero_idx >= 0:
                # 交换 first_zero 与 idx 的数值
                nums[idx], nums[next_zero_idx] = nums[next_zero_idx], nums[idx]
                last_zero_idx = next_zero_idx
                next_zero_idx = -1
                # 寻找下一个0的位置
                for _next_zero_idx in range(last_zero_idx + 1, len(nums)):
                    if nums[_next_zero_idx] == 0:
                        next_zero_idx = _next_zero_idx
                        break

        return nums


if __name__ == """__main__""":
    cases = [[0, 1, 0, 3, 12], [0], [0, 1], [1, 12, 3, 0, 0], [2, 1]]
    for c in cases:
        print(Solution().moveZeroes(c))


```