Reusable public libraries for [KatLang](https://katlang.org).

# Usage

In the KatLang web page, you can open libraries stored under `./libraries` using URLs such as:

```katlang
open 'https://katlang.org/libraries/vec.kat'
```

Library authors may organize `.kat` files in subfolders. The folder path is included in the library URL.

For example:

```katlang
open 'https://katlang.org/libraries/math/statistics.kat'
```

## Example
```
open 'https://katlang.org/libraries/vec.kat'

InitialSpeed = 30.3 // the approximate speed of a soccer ball when being kicked by a professional soccer player, 70 mph in m/s
InitialAngle = Math.Pi/6 // Assuming an initial angle of 30°
u_ = Vector(InitialSpeed*Math.Cos(InitialAngle), InitialSpeed*Math.Sin(InitialAngle), 0)
a_ = Vector(0, -9.8, 0)
v_ = Add(u_, Scale(a_,t))
s_ = Add(Scale(u_,t), Scale(a_,1/2*t^2))


'velocity and displacement at time = 0'
v_(0)
s_(0)

'velocity and displacement at time = 2.0'
v_(2.0)
s_(2.0)

'time, velocity and displacement at highest point'
t_highest = v_(0):_y/Math.Abs(a_:_y)
t_highest
v_(t_highest)
s_(t_highest)

'time, velocity and displacement when hitting back to the ground'
t_final = 2*(v_(0):_y)/Math.Abs(a_:_y)
t_final
v_(t_final)
s_(t_final)
```
Output
```
velocity and displacement at time = 0
26.2405697346685017, 15.15, 0
0.0, 0.00, 0.0
velocity and displacement at time = 2.0
26.2405697346685017, -4.45, 0.0
52.48113946933700340, 10.7000, 0.000
time, velocity and displacement at highest point
1.5459183673469387755102040816
26.2405697346685017, 0.000000000000000000000000000, 0
40.565778722472224566836734693, 11.710331632653061224489795919, 0
time, velocity and displacement when hitting back to the ground
3.0918367346938775510204081633
26.2405697346685017, -15.150000000000000000000000000, 0
81.13155744494444913367346939, -0.000000000000000000000000002, 0
```
# Contribution Guidelines

If you would like to contribute a KatLang library, please fork this repository, add your library as a `.kat` file in `./lib`; and edit the `libraries.json`, adding in your library details at the bottom.
Finally, create a pull request for your changes.

The `.kat` file should be named in the kebab case.

New libraries are suggested to adapt the MIT license, which the [KatLang language](https://github.com/katlangorg/katlangnet) is using,
while other [open-source licenses](https://opensource.org/licenses?categories=other-miscellaneous%2Cpopular-strong-community) are acceptable too.

If you have any queries, welcome to open an issue.
