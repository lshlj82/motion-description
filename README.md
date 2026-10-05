# Describing Motion

This is an interactive, browser-based demo of the first topic of general physics: position, velocity, and acceleration; vectors; and motion in two dimensions. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 위치·속도·가속도, 미분과 적분, 자유낙하, 진동운동, 좌표계, 벡터와 스칼라, 벡터 연산, 좌표 회전, 내적과 외적, 평형 조건, 포물체 운동, 운동의 독립성, 등속 원운동, 상대운동을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `motion-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `motion-en.html` | American English version |
| `motion-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts. For example, $v=\sqrt{2gd}$ and $\int_{t_i}^{t_f} a(t)\,dt$ are typeset rather than written as plain text.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/motion-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/motion-en.html` or `.../motion-ko.html`.

These pages can share a repository with the second-semester demos (`gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The fourteen sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Velocity:** On an $x(t)$ graph, the page draws the secant line over an interval $\Delta t$ alongside the tangent line at $t_0$. As you shrink $\Delta t$, the average velocity approaches the instantaneous velocity $dx/dt$. The readouts also show the sign of the acceleration and which way the curve bends.
2. **Acceleration and integrals:** Three stacked graphs show $a(t)$, $v(t)$, and $x(t)$ for constant acceleration, with a moving object on a track above them. The shaded areas under the graphs are $\Delta v$ and $\Delta x$, and the page checks the result against $\Delta x = (v^2 - v_0^2)/2a$.
3. **Free fall:** A ball is dropped on Earth, the Moon, or Mars and drawn with strobe images. The page gives the fall time $t=\sqrt{2d/g}$ and the landing speed $v=\sqrt{2gd}$.
4. **Oscillation:** A block on a spring is shown with live graphs of $a=\sin t$, $v=-\cos t$, and $x=-\sin t$, along with a readout confirming $a + x = 0$.
5. **Coordinates:** You can drag a point and read it in both Cartesian $(x, y)$ and polar $(r, \theta)$ form, with the conversion between the two.
6. **Displacement and distance:** A winding path runs between two points that you can drag. The page compares the displacement $|\Delta\vec r|$ with the length of the path.
7. **Vector algebra:** You can drag $\vec A$ and $\vec B$ and view $\vec A + \vec B$ (as a parallelogram), $\vec A - \vec B$, or $c\vec A$, with their components. The unit vectors $\hat i$ and $\hat j$ are also drawn.
8. **Rotating axes:** You can rotate the coordinate axes by an angle $\varphi$. The components of a vector change, but its length stays the same and the angles satisfy $\theta = \theta' + \varphi$.
9. **Dot and cross products:** You drag two vectors and set their $z$ components with sliders. The page computes $AB\cos\theta$ and checks it against $A_xB_x + A_yB_y + A_zB_z$. It also gives the full 3D cross product and checks that its size equals $AB\sin\theta$, shown as the shaded parallelogram. When both vectors lie in the $xy$ plane, the page marks whether $\vec A\times\vec B$ points out of the page (⊙) or into it (⊗).
10. **Equilibrium:** This is a force table with three hanging masses whose string directions you can adjust. It shows the net force, and a button finds the angles that balance the masses (120° apart when the masses are equal).
11. **Projectiles:** An animated trajectory shows the velocity vector and its components. The page gives the range $R$, the maximum height $h$, and the time of flight. It can also draw the 45° path and the complementary-angle path, which has the same range.
12. **Independence of motions:** One demo compares a dropped ball with a ball launched horizontally, and shows they stay at the same height. The other is the falling-target demo: a bullet aimed straight at a target that starts falling the moment the gun fires still hits it, because both fall by $\tfrac12gt^2$.
13. **Uniform circular motion:** The page draws the velocity (tangent to the circle) and the centripetal acceleration $v^2/r$ (toward the center), along with $\omega$, $T$, $f$, the arc length, and the components of both vectors.
14. **Relative motion:** An object is watched from the ground and from a moving car. The two velocity graphs, $\vec v_{PA}=\vec v_{PB}+\vec v_{BA}$, are parallel lines, so both observers measure the same acceleration.

## Notes on the model

- The drawings are schematic, not to scale. The numbers in the readouts are computed exactly from the formulas.
- The pages follow the system's light or dark setting.
- With `prefers-reduced-motion`, the oscillation and circular-motion animations start paused, and the header animation stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
