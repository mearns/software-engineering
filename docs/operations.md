# Operations

## Dashboards

Dashboards on TV screens, or whatever the remote-work equivalent is, are an antipattern. Humans shouldn't be looking at dashboards
to know if the system is healthy; humans should be **alerted by machines** when the system is unhealthy. Dashboards full of graphs
are great when you already know the system is unhealthy, and you're trying to understand why; they're a debugging tool.

If you have humans looking at graphs to detect when something goes wrong, ask yourself: _what are they looking for? Can a computer
look for that instead?_ Most of the time, the answer is "yes": spikes, dips, threshold breaches, even rapid rate changes can all be
trivially detected by a computer and usually comes built into your metric or dashboarding system.

If the humans are doing something more "nuanced" than that; your first questions should be: _How accurate are they? Do they actually know
what they're looking for?_ Don't get wrong, it would be a mistake to underestimate the intuition of someone highly experienced with
a system. But if they're that familiar with the system, do you really want to waste that resource having them stare at graphs all day?
You might need to spend some time thinking about what your system's true objectives are, and how you can measure them in a more straight
forward way.

Not everything needs an alert. Some teams have a regularly scheduled ritual of looking over their dashboards to see how things are
playing out in the long run, so they can make non-urgent adjustments as needed. This _might_ be a good use-case for a dashboard. On
the other hand, a report might be even better for this. If you can get a machine to detect what things need to be reviewed, you can
run this detection on a schedule and generate a report, so you're team can focus on only the important things.

