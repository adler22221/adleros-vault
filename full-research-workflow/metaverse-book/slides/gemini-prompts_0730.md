# 7/30発表 — Gemini画像生成プロンプト

**厳守事項**：すべてのプロンプトは英語で `absolutely no text, no letters, no numbers, no typography, no labels` で終える。
日本語ラベルは生成後にPowerPointでテキストボックスとして乗せる（`.pptx`内の該当スライドに、破線の枠として既に場所を空けてある）。

**手順**：
1. 下の①を最初に生成する
2. ①の生成結果を「スタイル参照画像」として、以降の②〜⑤の生成時に一緒にアップロードする（一貫した画風を保つため）
3. すべて **4:3** で生成する（16:9で生成すると主題が小さくなりすぎる。スライドの右40%程度に配置してトリミングする前提）
4. 生成後、各スライドの破線枠（imgframeのラベル参照）に配置し、その上に日本語ラベルを重ねる

**共通スタイル前文**（毎回プロンプトの先頭に付ける）：
```
Style: minimalist editorial illustration, flat design with subtle gradients,
limited palette of pine green (#2E6E5A), slate blue (#41678A), amber (#C98A2E),
deep navy (#16233B), warm gray (#6B7280). Clean geometric shapes, generous
negative space, soft diffused lighting, no photorealism. 4:3 aspect ratio.
```

---

## ① 表紙：ユニバースとメタバースに挟まれる人影（任意・優先度低）

```
[共通スタイル前文]
A small human silhouette standing at the center of a vertical divide between
two vast abstract backgrounds: on the left, a deep navy cosmos with subtle
star-like points of light suggesting immense age and constancy; on the right,
a shifting lattice of glowing blue-green geometric lines and nodes suggesting
a self-rewriting digital structure, slightly warped and unstable compared to
the left side. The figure is caught in the narrow gap between the two,
rendered small and vulnerable against both vast fields.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**：（表紙タイトル文字列自体は既にネイティブテキストとして配置済み。この絵は背景素材としてのみ使う）

---

## ② 作図③：四つの器官の無文字ループ図（スライド13）

**モチーフ**：ユクスキュルの機能環（Funktionskreis）——知覚器官（receptor）が環境から徴表（Merkzeichen／information, signs）を受け取り、環の内部規則（rules of the cycle）を経て、作用器官（effector）が効果徴表（Wirkzeichen）として環境に働きかけ返す、という一つの円環構造。4つの器官はこの単一の機能環を分業している：IoTが受容（知覚器官が卓越）、ビッグデータが保持（蓄積された徴表）、AIが規則（内部規則が卓越）、コードが作用（作用器官が卓越）。前のプロンプトは「空のノード＋矢印」でしかなく、器官の機能そのものが絵にならなかった——今回は各ノードの解剖そのものに知覚／規則／作用を描き込む。

```
[共通スタイル前文]
A circular flow diagram illustrating Jakob von Uexküll's functional-cycle
(Funktionskreis) model, applied to four technical organs arranged evenly
around one closed loop, in this fixed clockwise order:

1. First panel (a pure sensing/perception organ): dominated by a large
   concave funnel-shaped intake feature on its counter-clockwise edge,
   with small glowing particles of information visibly flowing inward
   into it. Its internal core (see below) is small and subdued.
2. Second panel (a retaining/storage organ): its intake and output
   features are modest, but its central core is rendered as a
   layered, strata-like archive shape — stacked translucent horizontal
   bands, as if accumulating incoming particles over time like
   sediment.
3. Third panel (an interpreting, rule-forming organ): its central core
   is the largest and most complex of the four — a crystalline,
   many-faceted glowing shape, clearly the most intricate structure in
   the whole image — while its intake and output features are modest.
4. Fourth panel (a pure effecting/acting organ): dominated by a large
   convex radiating beam feature on its clockwise edge, emitting a
   bright, sharp, directional glow outward — brighter and sharper than
   any other panel's output. Its internal core is small and subdued.

Every panel shares the same three-part anatomy at different scales: a
concave funnel-intake (perception organ / receptor) on its incoming
edge, a small central core (the rule governing how intake becomes
output) in the middle, and a convex radiating beam (effect organ /
effector) on its outgoing edge — only the emphasis differs per panel,
as described above. The four panels are connected by curved arrows
flowing clockwise, each arrow running from one panel's output-beam
directly into the next panel's intake-funnel, visibly made of small
glowing amber particles in motion along the arrow's path — showing
that one organ's effect becomes the next organ's perception. The loop
must be fully closed, with the fourth panel's output arrow curving
back around to the first panel's intake. Panels are plain blue-green
rounded rectangles with soft drop shadows; all functional-anatomy
features (funnels, cores, beams) are rendered as glowing structural
linework, not solid decorative fills, so they read as diagrammatic
anatomy rather than ornament. Centered composition, loop fills most of
the frame.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**（生成後、各ノードの中央に配置——上記の固定順序に対応）：
`IoT`（①漏斗＝受容器が卓越）／`ビッグデータ`（②地層状コア＝保持）／`AI`（③結晶コア＝規則が卓越）／`法としてのコード`（④放射ビーム＝作用器が卓越）
※各ノードにラベルが収まる余白（ノード幅の70%程度）を想定して生成させる

---

## ③ 作図④：石碑・紙の本 vs 光るサーバー室（スライド17・最優先）

```
[共通スタイル前文]
Split composition, left half and right half divided by a subtle vertical
seam. Left half: a weathered ancient stone stele with faint carved
inscriptions, next to a stack of old paper books, both bathed in warm
amber daylight, dust particles visible in a light beam, conveying slow
physical decay over centuries. Right half: a dark server room with rows
of glowing blue-green server racks, cables, and blinking status lights,
conveying opaque, humming, constantly-shifting digital infrastructure
hidden behind metal panels. The contrast should feel like "old and legible
decay" versus "new and illegible opacity."
absolutely no text, no letters, no numbers, no typography, no labels,
no screens with visible text or UI.
```
**PowerPointで乗せるラベル**：`昔：石碑・紙の書籍` ／ `今：Facebook・サーバー`（各半分の上部に配置）

---

## ④ 作図⑤：四段構造・最上段だけ床が抜けている図（スライド20）

```
[共通スタイル前文]
A vertical stack of four horizontal platforms/floors, stacked like
sedimentary layers, viewed from a slight three-quarter angle. The bottom
three floors rest solidly on a continuous foundation plane rendered in
solid navy, clearly connected to one another and to the ground beneath.
The top (fourth) floor is visually separated from the foundation by a
gap or crack of glowing amber light beneath it, appearing to float
detached from the common ground the other three share. Convey stability
below and precariousness at the top through composition alone.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**（下から順に）：`Type 1 生物的` ／ `Type 2 文明的` ／ `Type 3 グローバル` ／ `Type 4 偽境的`

---

## ⑤ 大鵬と厚い風（スライド23・任意）

```
[共通スタイル前文]
A massive mythical bird (in the visual spirit of Zhuangzi's Peng/大鵬)
with enormous outstretched wings, soaring above thick, visible layers of
wind rendered as flowing horizontal bands of pale blue-white, the wind
bands thick and substantial enough to visibly bear the bird's weight.
The bird faces upward and forward into open sky, dawn-colored gradient
background. Convey majesty that still visibly depends on and rests upon
something beneath it.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**：不要（比喩の絵として単独で使う）

---

## ⑥ 与件から引き剥がされた自己像（スライド9）

```
[共通スタイル前文]
A single human silhouette standing upright and detached, elevated on a
small isolated platform at the center of the frame. Below and around it,
a vast web of faint organic root-like threads spreads outward across the
lower two-thirds of the frame — but every thread bends and curves upward,
reaching toward the standing figure, as though the whole field exists to
answer to it rather than the figure being embedded within it. The threads
should thin and fade toward the edges. The figure itself is rendered
slightly larger and more solid than the threads, conveying command and
separateness rather than connection.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**：不要（スライド本文の主張文がすでに議論を運ぶ。この絵は純粋に補助的な視覚）

---

## ⑦ 一次〜三次の過去把持・予持（スライド13・最優先級——抽象概念の可視化）

```
[共通スタイル前文]
A horizontal flowing river of light representing the passage of time,
with a single bright vertical point of light at the center marking "now".
Immediately behind and ahead of this point, short warm amber wisps of
light curve gently backward and forward, close to the center, rendered
organically like breath or smoke — representing lived memory and
anticipation. Extending far beyond these short organic wisps, in both
directions toward the edges of the frame, a long rigid blue-green
cable-like or circuit-like trail runs steadily in a straight line, glowing
evenly — clearly extending much further into both the past and the future
than the short organic wisps do, representing an externalized, technical
memory and anticipation that outreaches lived experience.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**（生成後、該当箇所の下に小さく配置）：
`一次・二次過去把持／予持`（中央の短い有機的な部分の下）／`第三次過去把持／予持`（左右に伸びる長い直線部分の下）

---

## ⑧ ユーザーとしての人間／自足完成化する人工性（スライド15・二つの円と差し替え）

```
[共通スタイル前文]
Split composition, left and right halves. Left half: several relaxed
human silhouettes in easy, unburdened postures — sitting, reclining,
walking loosely — bathed in soft warm amber light, spaced with generous
open space between them, conveying ease and equal freedom, none of them
in a posture of effort or labor. Right half: a self-contained abstract
mechanical structure — an intricate glowing lattice of interlocking gears
and circuit-like nodes forming a closed loop, humming with its own
internal activity, rendered in cool blue-green and deep navy, conveying
quiet autonomous operation that needs no outside attention. A few faint
thin threads run from the human figures on the left toward the structure
on the right, suggesting burden flowing away from the humans into the
machine.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**：`ユーザー`（左半分の下）／`自足完成化する人工性`（右半分の下）
**注**：この絵が届くまでは、現行のネイティブ二円図（自己完結化／自足完成化）をそのまま残す——空白スライドにしない。届いた時点で二円をこの絵に差し替える。

---

## 補足：ネットから取得する写真（Geminiではなく検索）

- ~~鍵のかかったドアの写真（旧スライド5）~~ ——氷山の図（道・理・相の空間比喩、ネイティブ図形で実装済み）に差し替え、写真は不要になった
- **マカートニー使節団の乾隆帝謁見（1793年）**（スライド7・複数の世界）——Wikimedia Commonsで確認済みの3候補（すべてパブリックドメイン）：
  1. William Alexander画「The Approach of the Emperor of China to His Tent in Tartary to Receive the British Ambassador」（1793年、謁見の場面。**これを推奨**）
  2. William Alexander画「Lord Macartney Embassy To China 1793」（マカートニー初回会見の場面）
  3. James Gillray の風刺版画（1792年）——ただし三跪九叩頭問題を揶揄する戯画のため、学術発表の調子には不向き。非推奨
  ダウンロードは要確認（ユーザーの明示的な許可が必要なため、このスライドはまだ枠のみ）
- **Moltbookのフロントページ図版**（スライド18）——取得できない場合は引用ボックス（既にpptx側に用意済み）のまま使用。論証に必要なのは "Built for agents, by agents… Humans welcome to observe." という文言そのものなので、画面写真が無くても成立する
