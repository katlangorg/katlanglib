Official Reusable public libraries for [KatLang](https://katlang.org).

# Usage

In the KatLang web page, you can open libraries stored under `./libraries` using URLs such as:

```katlang
open 'https://katlang.org/libraries/vec.kat'
```

Library authors may organize `.kat` files in subfolders. The folder path is included in the library URL.

For example:

```katlang
open 'https://katlang.org/libraries/examples/algorithm.kat'
```

## Example
```
open 'https://katlang.org/libraries/plane-vec.kat', Math

InitialSpeed = 30.3 // the approximate speed of a soccer ball when being kicked by a professional soccer player, 70 mph in m/s
InitialAngle = Pi / 6 // Assuming an initial angle of 30°
u = Vector(InitialSpeed * Cos(InitialAngle), InitialSpeed * Sin(InitialAngle))
a = Vector(0, -9.8)
v = u.Add(a.Scale(t))
s = u.Scale(t).Add(a.Scale(0.5*t^2))

DisplayDecimals = 3

'velocity and displacement at time = 0'
v(0)
s(0)

'velocity and displacement at time = 2.0'
v(2.0)
s(2.0)

'time, velocity and displacement at highest point'
t_highest = v(0).Y / Abs(a.Y)
t_highest
v(t_highest)
s(t_highest)

'time, velocity and displacement when hitting back to the ground'
t_final = 2 * t_highest
t_final
v(t_final)
s(t_final)
```
Output
```
velocity and displacement at time = 0
26.241, 15.150
0.000, 0.000
velocity and displacement at time = 2.0
26.241, -4.450
52.481, 10.700
time, velocity and displacement at highest point
1.546
26.241, 0.000
40.566, 11.710
time, velocity and displacement when hitting back to the ground
3.092
26.241, -15.150
81.132, 0.000
```
# Contribution Guidelines

If you would like to contribute a KatLang library, please fork this repository, add your library as a `.kat` file in `./lib`; and edit the `libraries.json`, adding in your library details at the bottom.
Finally, create a pull request for your changes.

The `.kat` file should be named in the kebab case.

New libraries will adapt the MIT license, which the [KatLang language](https://github.com/katlangorg/katlangnet) is using.

If you have any queries, welcome to open an issue.
