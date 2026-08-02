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

```
[共通スタイル前文]
A circular flow diagram with exactly four empty rounded rectangular nodes
arranged evenly around a circle, connected by curved arrows flowing
clockwise from one node to the next, forming a closed loop. The arrows
should be clearly directional (arrowheads visible) and slightly glowing
amber to suggest active energy flow. The nodes themselves are plain empty
blue-green rounded panels with soft drop shadows, ready to receive labels.
Centered composition, loop fills most of the frame.
absolutely no text, no letters, no numbers, no typography, no labels.
```
**PowerPointで乗せるラベル**（4ノードそれぞれの中央に、生成後に配置）：
`AI` ／ `ビッグデータ` ／ `IoT` ／ `法としてのコード`
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

## 補足：ネットから取得する写真（Geminiではなく検索）

- **鍵のかかったドアの写真**（スライド5・道理相の例示）——Unsplash/Pexels等、再配布可のものを検索。出典をスライド隅に小さく記載
- **Moltbookのフロントページ図版**（スライド18）——取得できない場合は引用ボックス（既にpptx側に用意済み）のまま使用。論証に必要なのは "Built for agents, by agents… Humans welcome to observe." という文言そのものなので、画面写真が無くても成立する
