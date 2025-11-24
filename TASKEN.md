# Sort by Distance from Ideal

Problem Statement:
Given an integer array nums and a target value target (which can be either a single integer or an array of integers), sort the array according to the following rules:

    Numbers are sorted by the minimum difference between the number and any element in target (if target is an array) or simply the difference from target (if it's a single number)

    If two numbers have the same difference, the one closer to the mean of the entire array should come first

    If still tied, the smaller number comes first

Example 1:
text

Input: nums = [1, 5, 9, 3, 7], target = 4
Output: [3, 5, 1, 7, 9]

Explanation:

    Differences: |3-4|=1, |5-4|=1, |1-4|=3, |7-4|=3, |9-4|=5

    3 and 5 both have difference 1, but array mean = 5, |3-5|=2, |5-5|=0 → 5 is closer to mean, so 5 comes after 3

Example 2:
text

Input: nums = [10, 2, 8, 15, 12], target = [5, 13]
Output: [8, 12, 10, 15, 2]

Explanation:

    Min differences: min(|8-5|,|8-13|)=5, min(|12-5|,|12-13|)=1, min(|10-5|,|10-13|)=3, min(|15-5|,|15-13|)=2, min(|2-5|,|2-13|)=3

    Sort by difference: 12(1), 15(2), 10(3), 2(3), 8(5)

    10 and 2 both have difference 3, mean = 9.4, |10-9.4|=0.6, |2-9.4|=7.4 → 10 is closer

Constraints:

    1 <= nums.length <= 10^4

    -10^5 <= nums[i] <= 10^5

    target can be integer or array of integers with length 1 to 100
