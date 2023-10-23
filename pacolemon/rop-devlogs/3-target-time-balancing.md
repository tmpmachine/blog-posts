First draft : 23 Oct 2023

Revisions : 3

# Time Balancing - ROP Time Management System Devlog #3

The core of the Ratio of Priority (ROP) time management system is target time balancing or Time Balancing (TB) for short. The purpose of TB is to help the user reach balance in their work by making sure they're spending the minimum amount of time required by each task.

Time balancing is an automated process that happens when progress is made on a task.

When a TB happens, a newly added progress is distributed to every other task's target time based on their ROP.

## Example

In below example, we have 3 tasks with a total of 100% ROP and zero progress.

No | Task                     | ROP | Progress (minutes)
-- | --                       | --  | -- 
1  | Practice music           | 50% | 0
2  | Practice web development | 25% | 0
3  | Write a blog post        | 25% | 0

Let's say we made some progress on task 1 for 30 minutes, this progress will be distributed to every other task's target time, calculated with the following equation :
```
j = 1
for i = 1:N, i != j
  targetTime[i] = targetTime[i] + minutesToDistribute * ( ratio[i] / remainingRatio )
```
Where `remainingRatio` and `minutesToDistribute` are the remaining ratio and remaining progress of `task[j]` if it were at 100% ROP. These values can be retrieved with the following equation :
```
remainingRatio = 100 - ratio[j]
minutesToDistribute = ( addedMinutes *  ( remainingRatio / 100 ) ) / ( ratio[j] / 100 )
```

The calculated target time can then be stored in a new column, Target time.

No | Task                     | ROP | Progress (minutes) | Target time (minutes)
-- | --                       | --  | --                 | --
1  | Practice music           | 50% | 30                 | 0
2  | Practice web development | 25% | 0                  | 15 
3  | Write a blog post        | 25% | 0                  | 15

## Consistent Progress
With automated target time assigned by the system, it's now possible to have a consistent progress without day-to-day planning.

Wether the user left a task half done or exceed the given target, they are guaranteed to know precisely how much time needed to reach balanced progress.

### ROP Adjustment
ROP adjustment is often performed after the user have made some progress on the task list. Because of this, the user should be given options to adjust a task's target time freely or leave it as is.

Any time balancing happened after ROP adjustment must incorporate the new ROP into its equation.
