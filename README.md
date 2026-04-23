# HUNGERGAMES-SYS
なんかそういうの

# 能力 (kit) 一覧

全 26 種。選択は `/kit` コマンド (または `/kit list` で一覧、`/kit <id>` で直接選択)。
能力専用の装備には `[system]` タグが付き、死亡時にドロップしません。

## 能力早見表

| 能力名 | id | HP | アイコン | 一言 |
|---|---|---|---|---|
| 戦士 -Warrior- | `warrior` | 20 | IRON_SWORD | 命中時に STRENGTH I (2秒) |
| 射手 -Archer- | `archer` | 16 | BOW | 矢命中で SLOW I (3秒) |
| 斥候 -Scout- | `scout` | 16 | IRON_AXE | 恒常 SPEED I / 鉤縄ベクトル / 落下ダメ無効 |
| 衛生兵 -Medic- | `medic` | 20 | SPLASH_POTION | 右クリで即 8HP 回復 |
| 拳闘家 -Brawler- | `brawler` | 22 | FISHING_ROD | Knockback II で敵を場外へ |
| 跳ね兎 -Kangaroo- | `kangaroo` | 16 | RABBIT_FOOT | JUMP BOOST II / 落下ダメ無効 |
| 圧殺者 -Stomper- | `stomper` | 22 | IRON_BOOTS | 落下ダメ無効 + 着地 AoE |
| 毒牙 -Viper- | `viper` | 18 | SPIDER_EYE | 命中で POISON II (4秒) |
| 火魔 -Pyro- | `pyro` | 20 | FLINT_AND_STEEL | 恒常炎耐性 + 着火 5秒 |
| 忍者 -Ninja- | `ninja` | 14 | ENDER_PEARL | スニーク中 INVISIBILITY / 透明中の命中で死の宣告 (30s / CD 180s) |
| 盾衛士 -Tank- | `tank` | 30 | IRON_CHESTPLATE | 恒常 RESISTANCE I + SLOWNESS I |
| 雷神 -Thor- | `thor` | 18 | BLAZE_ROD | 杖右クリで 20〜35m 先に落雷 |
| バーサーカー -Berserker- | `berserker` | 6 → 40 | NETHERITE_AXE | HP 6 開始、キル毎に +2 HP / +0.5 攻撃 |
| 吸血鬼 -Vampire- | `vampire` | 20 | REDSTONE | 昼 被ダメ ×1.5 / 夜 与ダメ ×1.5 |
| 波神 -Poseidon- | `poseidon` | 18 | TRIDENT | Loyalty トライデント / 水中雨天で与ダメ ×1.5 |
| 槍兵 -Lancer- | `lancer` | 20 | IRON_SPEAR | 長槍の近接 +5 ダメ / スプリント中 +2 |
| 鎧武者 -Cuirassier- | `cuirassier` | 24 | NETHERITE_CHESTPLATE | 胴のみ装着、大ダメ時 ×0.55 軽減 |
| ストーカー -Tracker- | `tracker` | 18 | COMPASS | コンパス右クリで最寄り生存者の座標と距離 (CD 5s) |
| スリ -Thief- | `thief` | 18 | BLAZE_ROD | 対象を右クリでインベ開閲 (slot 9-35) / 5m 離れると閉鎖 (CD 10s) |
| トロール -Troll- | `troll` | 18 | MAGENTA_WOOL | KB II 棒で大跳ね + 歩行で地面が虹色羊毛 |
| 極 -LastManStanding- | `lastmanstanding` | 2 | SKELETON_SKULL | 装備なし / 弓矢命中で即死級 |
| 葬儀屋 -Mortician- | `mortician` | 20 | BONE | キル時に遺体位置にチェスト生成、周囲ドロップを格納 |
| 溶岩鶏 -LavaChicken- | `lavachicken` | 20 | LAVA_BUCKET | マグマバケツ×3 / 卵×10スタック / 恒常 SLOW_FALLING |
| 導矢 -Homing- | `homing` | 16 | ARROW | 発射した矢が重力無視で射手の視線方向に追従 (10秒) |
| 月詠 -Tsukuyomi- | `tsukuyomi` | 16 | PHANTOM_MEMBRANE | 1秒視線中心で捉えた対象だけに偽の夜 + BLINDNESS (5秒 / CD 60s) |
| 鏡像壁 -MirrorWall- | `mirrorwall` | 18 | TINTED_GLASS | 前方 2m に 3×3 偽ガラスで飛び道具反射 (4秒 / CD 30s) |

> **封印中 (ProtocolLib 対応待ち)**: 影分身 (shadowclone) / 幻像 (illusion) — クラスは残っているが `KitRegistry` の登録をコメントアウトしている。

---

## 詳細

### 戦士 -Warrior-
- **id**: `warrior`
- **HP**: 20
- **装備**: 鉄剣 / 革一式 / 金のりんご / パン×4
- **能力**: 反撃の咆哮 — 敵に命中時、自分に STRENGTH I (2秒)

### 射手 -Archer-
- **id**: `archer`
- **HP**: 16
- **装備**: Power I 弓 / 木剣 / 矢×32 / 革一式 / パン×4
- **能力**: 風詠み — 矢を命中させた敵に SLOW I (3秒)

### 斥候 -Scout-
- **id**: `scout`
- **HP**: 16
- **装備**: 鉄斧 / チェーン胴脚 / 革兜靴 / 鉤縄 (釣り竿) / パン×4
- **能力**:
  - 疾風の足 — 試合中ずっと SPEED I (恒常)
  - 鉤縄 — 釣り竿のフック位置へベクトル飛翔
  - 軽身 — 落下ダメージ無効

### 衛生兵 -Medic-
- **id**: `medic`
- **HP**: 20
- **装備**: 石剣 / 革一式 / 金のりんご×2 / 回復ポーション×3 / パン×4
- **能力**: 応急処置 — 回復ポーションは右クリックで即 8HP 回復

### 拳闘家 -Brawler-
- **id**: `brawler`
- **HP**: 22
- **装備**: Knockback II 木剣 / 釣り竿 / 革一式 / パン×4
- **能力**: 大男の拳 — 強力なノックバックで敵の足場を奪う

### 跳ね兎 -Kangaroo-
- **id**: `kangaroo`
- **HP**: 16
- **装備**: 石斧 / 革一式 / パン×4
- **能力**:
  - 反重力 — 恒常 JUMP BOOST II
  - 羽根の着地 — 落下ダメージを完全無効化

### 圧殺者 -Stomper-
- **id**: `stomper`
- **HP**: 22
- **装備**: 鉄斧 / 鉄靴 / 革胴脚兜 / パン×4
- **能力**: 地響き — 落下ダメ無効 + 半径 4 ブロック内の敵へ落下距離分のダメージ

### 毒牙 -Viper-
- **id**: `viper`
- **HP**: 18
- **装備**: 石剣 / 革一式 / 金のりんご / パン×4
- **能力**: 毒の牙 — 攻撃命中時、相手に POISON II (4秒)

### 火魔 -Pyro-
- **id**: `pyro`
- **HP**: 20
- **装備**: FireAspect II 木剣 / チェーン胴 / 革脚兜靴 / 火打石と打ち金 / パン×4
- **能力**:
  - 紅蓮の纏衣 — 恒常 FIRE_RESISTANCE (炎/溶岩/火打を無効化)
  - 着火 — 攻撃命中時に相手を 5 秒炎上

### 忍者 -Ninja-
- **id**: `ninja`
- **HP**: 14
- **装備**: 鉄剣 / 革一式 / エンダーパール×2 / パン×4
- **能力**:
  - 幻影 — スニーク中は INVISIBILITY で姿を消す (装備は見えるので身軽さが鍵)
  - 死の宣告 — 透明時に敵へ命中すると 30 秒以内に倒さねば自動処刑 (忍者のキル扱い)
- **制約**: 死の宣告のクールダウンは **180 秒** (`IRON_SWORD` の Material cooldown で管理 / `hasCooldown` ガード付き)

### 盾衛士 -Tank-
- **id**: `tank`
- **HP**: 30
- **装備**: 鉄胴 / 鉄兜 / チェーン脚靴 / 石剣 / パン×4
- **能力**:
  - 鉄壁 — 恒常 RESISTANCE I (被ダメ -20%)
  - 代償: 鈍足 — 恒常 SLOWNESS I

### 雷神 -Thor-
- **id**: `thor`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 雷の杖 / パン×4
- **能力**: 神鳴 — 杖を右クリで視線先 20〜35 マスのブロックに落雷
- **制約**: 近すぎ/遠すぎは不発 / CD 15秒

### バーサーカー -Berserker-
- **id**: `berserker`
- **HP**: 6 (開始) → 最大 40
- **装備**: Sharpness III 鉄剣 / 防具無し
- **能力**: 血戦
  - キル毎に最大体力 +2 (上限 HP 40)
  - キル毎に攻撃力 +0.5 (上限 +5)

### 吸血鬼 -Vampire-
- **id**: `vampire`
- **HP**: 20
- **装備**: チェーン一式 / 鉄剣 / パン×4
- **能力**:
  - 陽光 — 昼は被ダメージ ×1.5
  - 夜天 — 夜は与ダメージ ×1.5
- **告知**: 昼夜切替のタイミングで Title + SE 通知

### 波神 -Poseidon-
- **id**: `poseidon`
- **HP**: 18
- **装備**: 波神の銛 (Trident, Loyalty III + Impaling III + Unbreaking III) / 革一式 / パン×4
- **能力**:
  - 忠義の銛 — Loyalty 付きで投擲後に手元へ戻る
  - 潮騒 — 水中 / 雨天で与ダメージ ×1.5

### 槍兵 -Lancer-
- **id**: `lancer`
- **HP**: 20
- **装備**: 穿孔の長槍 (Iron Spear / Unbreaking III) / 鉄ヘルム / 鉄脚 / 鉄ブーツ / パン×4
- **能力**:
  - 穿孔 — 長槍での近接命中時ダメージ +5
  - 突撃 — スプリント中の命中で追加 +2
- **補足**: 武器は Paper 26.1.2 で追加された `IRON_SPEAR` を使用 (Trident は Poseidon 専用と差別化)。胴は空けて軽装に寄せる

### 鎧武者 -Cuirassier-
- **id**: `cuirassier`
- **HP**: 24
- **装備**: 石剣 / 銘入り胴鎧 (Netherite Chestplate, Protection III + Unbreaking III) / パン×4
- **能力**: 鉄壁の胴 — 大ダメージ (3.0↑) を ×0.55 に軽減
- **特徴**: 頭・脚・足は装着しない (胴のみ)

### ストーカー -Tracker-
- **id**: `tracker`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 追跡のコンパス / パン×4
- **能力**: 追跡 — コンパス右クリで最寄り生存プレイヤーの座標+距離をチャット表示、コンパスの針もその方向へ
- **制約**: CD 5 秒 / 無敵時間中は発動不可

### スリ -Thief-
- **id**: `thief`
- **HP**: 18
- **装備**: 石剣 / 革一式 / 盗みの棒 (Blaze Rod) / パン×4
- **能力**: 拝借 — プレイヤーを右クリでインベントリの非ホットバー枠 (slot 9-35) を 27 スロット chest として開閲、持ち出した物が相手のインベから消える
- **制約**: 対象から 5 マス以上離れると自動クローズ / CD 10 秒 / 無敵時間中は発動不可 / chest への押し込み不可 (持ち出し一方通行)

### トロール -Troll-
- **id**: `troll`
- **HP**: 18
- **装備**: KB II 木の棒 / 革一式 / パン×4
- **能力**:
  - 大跳ね — トロールの棒で殴ると KB II + 追加 velocity で約 6 マス吹き飛ばす
  - 虹の歩 — ブロック単位で歩くたびに足元のブロックがカラフルな羊毛に変わる (羊毛上では再変化しない)

### 極 -LastManStanding-
- **id**: `lastmanstanding`
- **HP**: 2 (ハート 1)
- **装備**: なし (素手スタート)
- **能力**: 一矢 — 弓矢命中で即死級ダメージ (e.setCancelled + 次 tick に 99999 ダメ投入)
- **特徴**: 弓・矢・装備は現地で 1 から作り揃える覚悟が要る

### 葬儀屋 -Mortician-
- **id**: `mortician`
- **HP**: 20
- **装備**: 鉄剣 / 革一式 / パン×4
- **能力**: 遺品箱 — キル時に遺体位置の足元にチェスト生成、周囲半径 3m の Item entity を吸い込んで格納

### 溶岩鶏 -LavaChicken-
- **id**: `lavachicken`
- **HP**: 20
- **装備**: マグマバケツ×3 (ホットバー 0-2) / 卵×10 スタック (各 16 個、ホットバー 3-8 + 主インベ 9-12)
- **能力**:
  - 羽根 — 恒常 SLOW_FALLING で落下速度が常に低下
  - 熔岩撒き — マグマバケツで足場を溶岩に沈める
  - 弾幕 — 卵を大量に投げて視界と足場を乱す (稀に雛が出る)
- **補足**: Minecraft 映画の『Lava Chicken』モチーフ。武器/防具は無く、熔岩と卵で戦う変則型

### 導矢 -Homing-
- **id**: `homing`
- **HP**: 16
- **装備**: 素弓 / 木剣 / 矢×24 / 革一式 / パン×4
- **発動**: 弓を右クリで射撃
- **能力**: 導矢 — 発射した矢は **重力無視** + 毎 tick **射手の視線方向** に完全同期して velocity を更新
- **制約**:
  - 発射速度 0.55 倍 (通常弓より遅く、避けやすい)
  - 追尾中の巡航速度 0.9 block/tick 固定
  - 矢のダメージは 0.5 倍 (素弓基礎 2.0 → 1.0)
  - 命中 / ブロック接触 / 10 秒経過で追尾解除
  - 射手が視線を動かせば矢も追従する (敵ロック不要)

### 月詠 -Tsukuyomi-
- **id**: `tsukuyomi`
- **HP**: 16
- **装備**: 鉄剣 / 革一式 / ファントムの膜 / パン×4
- **能力**: 月詠 — 右クリでロック開始。1 秒 (20 tick) 視線中心 (cos 0.92 / 30m) に対象を捉え続けると発動 → `setPlayerTime(18000, false)` で対象だけに偽の夜 + BLINDNESS 5 秒
- **制約**: ロック最長 4 秒でタイムアウト / CD 60 秒

### 鏡像壁 -MirrorWall-
- **id**: `mirrorwall`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 黒色ガラス / パン×4
- **能力**: 鏡像壁 — 右クリで前方 2m に 3×3 の TINTED_GLASS を **実ブロック** で設置。矢/トライデント等を完全遮断する物理的な壁
- **制約**: 設置先が空気でないと失敗 / 4 秒で自動消滅 (air に戻る) / CD 30 秒

### 影分身 -Shadowclone- §8(封印中)
- **id**: `shadowclone`
- **HP**: 18
- **状態**: `KitRegistry` で登録コメントアウト (Paper 26.1.2 対応版 ProtocolLib 待ち)
- クラス・リスナーは残置しているので、ProtocolLib 対応次第で 1 行復活で有効化可能

### 幻像 -Illusion- §8(封印中)
- **id**: `illusion`
- **HP**: 16
- **状態**: Shadowclone と同じ理由で登録コメントアウト。Session/反撃ロジックは残置

---

## カスタムレシピ

プラグインが登録する `ShapedRecipe` / `ShapelessRecipe`。`RecipeRegistry` で一括管理しプラグイン停止時に削除されます。

| レシピ ID | 型 | 材料 | 結果 |
|---|---|---|---|
| `hungergames:cheap_arrow` | Shaped | 火打ち石(上) + 棒(下) | 矢 ×2 |
| `hungergames:food_bowl_heal` | Shapeless | 食べ物 1 種 + 木の皿 (BOWL) | 民間治療薬 (HEALING Potion) |

`food_bowl_heal` の食べ物は `MaterialChoice` で列挙している: BREAD / APPLE / 各種肉 (生・調理済み) / 魚 / 野菜 / 果実 / GOLDEN_APPLE / HONEY_BOTTLE など。

## MobLoot (動物ドロップ)

- 生肉は自動で焼肉版に置換 (`BEEF→COOKED_BEEF` 等)
- **動物 (`Animals` 系: 牛/豚/羊/鶏/ウサギ等) を倒すと 0〜2 本の糸を追加ドロップ** (バニラ弓のクラフト材料を入手可能に)
- ゾンビ等モンスターは対象外
