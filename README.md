# Newton's Laws of Motion

This is an interactive, browser-based demo of Newton's laws. It covers the three laws, gravity and weight, normal force and action–reaction pairs, tension, friction, drag, and the forces in circular motion. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 뉴턴의 제1·2·3법칙, 중력과 무게, 수직항력과 작용–반작용 쌍, 비탈면, 애트우드 기계, 도르래, 블록 밀기, 엘리베이터, 마찰력, 항력과 종단속력, 커브길의 구심력을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `newton-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `newton-en.html` | American English version |
| `newton-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/newton-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/newton-en.html` or `.../newton-ko.html`.

These pages can share a repository with the other demos in the series (`motion-*`, `gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The twelve sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Second (and first) law:** Two opposing forces act on a block, and you watch $a = \Sigma F/m$ along with the graphs of $v(t)$ and $x(t)$. When the net force is zero, the block stays at rest. Side boxes cover the restoring force $F = -mx$ and inertial frames.
2. **Third law:** Two carts push apart. The forces on them are equal and opposite, but the lighter cart gets the larger acceleration, and the total momentum stays at zero.
3. **Gravity and weight:** Two balls of different mass fall together on Earth, the Moon, or Mars. The page gives each ball's weight in newtons, the reading on a scale calibrated for Earth, and the fall time $\sqrt{2h/g}$.
4. **Normal force:** A stone rests on a table, with all eight forces shown and the four action–reaction pairs highlighted one at a time. A scale under the stone reads $mg$; a scale under the table reads $(m+M)g$.
5. **Incline:** A block slides down a frictionless incline. Gravity is resolved into $mg\sin\theta$ and $mg\cos\theta$, and the page gives $a = g\sin\theta$, the time $t=\sqrt{2d/g\sin\theta}$, and the speed $v=\sqrt{2gd\sin\theta}$.
6. **Atwood machine:** The page computes $a = \frac{m_2-m_1}{m_1+m_2}g$ and $T = \frac{2m_1m_2}{m_1+m_2}g$, then animates the motion with free-body arrows.
7. **Table and pulley:** A hanging mass pulls a block across a table, with $a = \frac{m}{M+m}g$ and $T = \frac{Mm}{M+m}g$.
8. **Pushing two blocks:** A force pushes two blocks in contact. Free-body diagrams drawn apart show the action–reaction pair, with $F_{AB} = \frac{m_B}{m_A+m_B}F_\text{app}$.
9. **Elevator:** An elevator makes a round trip while the scale shows $N = m(g+a)$. A graph of the scale reading tracks each phase of the ride.
10. **Friction:** You pull a block along the floor, and the graph of $f$ against $F$ shows static friction rising to $\mu_s N$ and then dropping to kinetic friction $\mu_k N$. You can also tilt an incline until the block slips, at $\tan\theta_0 = \mu_s$.
11. **Drag and terminal speed:** This section follows a raindrop, a skydiver, or a ping-pong ball. An animation drops the object side by side with an identical object that feels no drag, showing the drag force $D$ growing until it balances $mg$. The page plots $v(t) = v_t\tanh(gt/v_t)$ and gives the terminal speed $v_t=\sqrt{2mg/C\rho A}$. For the raindrop, the terminal speed is about 27 km/h; with no drag it would land at about 550 km/h.
12. **Curves:** On a flat road, the required $\mu_s = v^2/rg$ is compared with what the road can supply. On a banked road, the ideal angle is $\tan\theta = v^2/gr$. The car holds the curve or skids, and a cross-section shows the forces.

## Notes on the model

- **Gravity:** The pages use $g = 9.8\ \text{m/s}^2$ on Earth, $1.62$ on the Moon, and $3.71$ on Mars.
- **Drag:** Air density is taken as $\rho = 1.2\ \text{kg/m}^3$. The speed curve uses the exact solution for drag proportional to $v^2$.
- **Animations:** Some animations are slowed down so the motion is easy to follow. The readouts always show real values.
- **Light and dark mode:** The pages follow the system's light or dark setting.
- **Reduced motion:** Under `prefers-reduced-motion`, the second-law, third-law, and elevator demos start paused, and the header animation stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
