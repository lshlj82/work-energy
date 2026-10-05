# Work and Energy

This is an interactive, browser-based demo of work, kinetic energy, potential energy, and the conservation of energy. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 일, 변하는 힘이 한 일, 일–운동에너지 정리, 중력과 용수철이 한 일, 일률, 보존력과 퍼텐셜에너지, 역학적 에너지 보존, 마찰 없는 궤도, 퍼텐셜에너지 곡선 읽기, 마찰과 열에너지를 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `energy-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `energy-en.html` | American English version |
| `energy-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/energy-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/energy-en.html` or `.../energy-ko.html`.

These pages can share a repository with the other demos in the series (`motion-*`, `newton-*`, `gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The eleven sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Work:** A force acts at an angle on a moving block. The page shows $W = F\Delta r\cos\theta$, the component of the force along the motion, and the sign of the work.
2. **Varying force:** You choose a force $F(x)$ and the limits $x_i$ and $x_f$. The work is the area under the curve, with positive and negative parts shaded and integrated numerically.
3. **Work–kinetic energy theorem:** A force acts on a block over a distance $d$. Energy bars show $K_i + W = K_f$, along with the final speed (or the stopping distance when the force opposes the motion). A side note covers action and reaction.
4. **Work by gravity:** The block can be thrown up, move down, or be lifted or lowered slowly by hand. The page shows $W_g = mgd\cos\varphi$, $v_f = \sqrt{v_i^2 \pm 2gd}$, and $W_a + W_g = 0$.
5. **Work by a spring:** A block on a spring moves between two positions. On the graph of $F = -kx$, the shaded area is $W_s = \tfrac12 kx_i^2 - \tfrac12 kx_f^2$, and the page says whether the block speeds up or slows down.
6. **Power:** A motor lifts a crate. The page shows $P = \mathbf F\cdot\mathbf v = mgv$, the time, the work, and the energy in kWh.
7. **Conservative forces:** You compare the work along two paths from a to b, and around the closed loop, for gravity and for kinetic friction. Gravity's work doesn't depend on the path; friction's does.
8. **Conservation of mechanical energy:** A pendulum is simulated with RK4. Energy bars and a time graph show $K$ and $U$ trading back and forth while $K + U$ stays constant.
9. **Frictionless track:** A block slides on a track whose start height and hill height you can change. Its speed follows $v = \sqrt{2g(h_0 - y)}$, and it turns back if the hill is taller than the starting height.
10. **Reading $U(x)$:** A particle moves on a potential energy curve, with the energy line and the allowed region shown. The page plots $F = -dU/dx$ and marks the stable and unstable equilibrium points.
11. **Friction and thermal energy:** A pushed block slides against friction. The page splits the work as $W = Fd = \Delta E_\text{mec} + \Delta E_\text{th}$, with $\Delta E_\text{th} = f_k d$. The text also covers the conservation of total energy and the power $P = dE/dt$.

## Notes on the model

- **Gravity:** The page uses $g = 9.8\ \text{m/s}^2$.
- **Path comparison:** The two paths in section 7 use $m = 1\ \text{kg}$, and the friction case uses $\mu_k = 0.5$.
- **Time scale:** Some animations are slowed down so the motion is easy to follow, but every readout shows the real values.
- **Light and dark:** The page follows the system's light or dark setting.
- **Reduced motion:** If `prefers-reduced-motion` is set, the header animation stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
