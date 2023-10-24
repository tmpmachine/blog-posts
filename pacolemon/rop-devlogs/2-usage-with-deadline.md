First draft : 22 Oct 2023

Revisions : 5

[Blog post](https://pacolemon.blogspot.com/2023/10/a-time-constrained-case-rop-devlog-2.html)

# A Time Constrained Case - ROP Time Management System Devlog #2

Ratio of Priority (ROP) time management system works great to develop long term hobbies with no predetermined deadline, but there's always a flip side of the coin.

One of the questions arised by XG (PacoLemon team member) is how the system would work if it were used in a time-constrained case, a deadline.

While the ROP time management system not designed for time-constrainted case, it can handle them just fine up to a certain level.

# Result on A Week Long Experiment

Let's take office working hours for the case.

My tasks rarely have due date set on them, but it's usually expected to be completed within three working days.

Before ROP, I would make a to do list ordered by priority level and just get done with it.

```
# Web Development Project

To do :
- Develop feature A
- Initial test on feature A
- Develop feature B
. (..)
```

When I tried applying ROP, however, what's changed is that it becomes easier to maintain the quality of my work. 

In addition to previous to do list, I now have a table of minimum required time to produce quality work.

The target time values on this table are the result of Time Balancing (TB), an automated process by the system.

No | Task                     | ROP | Progress (minutes) | Target time (minutes)
-- | --                       | --  | --                 | --
1  | Just write the code      | 75% | 180                | 0
2  | Initial test             | 18% | 0                  | 43
3  | Write documentation      | 7%  | 0                  | 16

To put it simply, I could produce a more polished output simply by not neglecting the minimum working time required by crucial parts of the work.

It is all but a week-long experiment, so there could be more to it.
