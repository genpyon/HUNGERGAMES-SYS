# HUNGERGAMES-SYS
なんかそういうの

# 能力 (kit) 一覧

全 27 種が有効登録。選択は `/kit` コマンド (または `/kit list` で一覧、`/kit <id>` で直接選択)。
能力専用の装備には `[system]` タグが付き、死亡時にドロップしません。また Q キーでのドロップもキャンセルされます。

## 能力早見表

| 能力名 | id | HP | アイコン | 一言 |
|---|---|---|---|---|
| 戦士 -Warrior- | `warrior` | 20 | IRON_SWORD | 命中時に STRENGTH I (2秒) |
| 射手 -Archer- | `archer` | 16 | BOW | 矢命中で SLOW I (3秒) |
| 斥候 -Scout- | `scout` | 16 | IRON_AXE | 恒常 SPEED I / 鉤縄ベクトル / 落下ダメ無効 |
| 衛生兵 -Medic- | `medic` | 20 | SPLASH_POTION | 医療ポーションで即 8HP 回復 |
| 拳闘家 -Brawler- | `brawler` | 22 | FISHING_ROD | Knockback II で敵を場外へ |
| 跳ね兎 -Kangaroo- | `kangaroo` | 16 | RABBIT_FOOT | JUMP BOOST II / 落下ダメ無効 |
| 圧殺者 -Stomper- | `stomper` | 22 | IRON_BOOTS | 落下ダメ無効 + 着地 AoE (敵が近くにいる時のみ) |
| 毒牙 -Viper- | `viper` | 18 | SPIDER_EYE | 命中で POISON II (4秒) |
| 火魔 -Pyro- | `pyro` | 20 | FLINT_AND_STEEL | 恒常炎耐性 + 着火 5秒 |
| 忍者 -Ninja- | `ninja` | 14 | ENDER_PEARL | シフト透明 / 透明解除後の命中で死の宣告 (CD 180s / 透明化ロック 15s) |
| 盾衛士 -Tank- | `tank` | 30 | IRON_CHESTPLATE | 恒常 RESISTANCE I + SLOWNESS I |
| 雷神 -Thor- | `thor` | 18 | BLAZE_ROD | 杖右クリで 20〜35m 先に落雷 (CD 15s) |
| バーサーカー -Berserker- | `berserker` | 6 → 40 | NETHERITE_AXE | HP 6 開始、キル毎に +2 HP / +0.5 攻撃 |
| 吸血鬼 -Vampire- | `vampire` | 20 | REDSTONE | 昼 被ダメ ×1.5 / 夜 与ダメ ×1.5 |
| 波神 -Poseidon- | `poseidon` | 18 | TRIDENT | Loyalty トライデント / 水中雨天で与ダメ ×1.5 |
| 槍兵 -Lancer- | `lancer` | 20 | IRON_SPEAR | 長槍の近接 +5 ダメ / スプリント中 +2 |
| 鎧武者 -Cuirassier- | `cuirassier` | 24 | NETHERITE_CHESTPLATE | 胴のみ装着、大ダメ時 ×0.55 軽減 |
| ストーカー -Tracker- | `tracker` | 18 | COMPASS | コンパス右クリで最寄り生存者の座標と距離 (CD 5s) |
| スリ -Thief- | `thief` | 18 | BLAZE_ROD | 対象を右クリでインベ開閲 / 5m 離れると閉鎖 (CD 10s) |
| トロール -Troll- | `troll` | 18 | MAGENTA_WOOL | KB II 棒で大跳ね + 歩行で地面が虹色羊毛 |
| 極 -LastManStanding- | `lastmanstanding` | 2 | SKELETON_SKULL | 装備なし / 弓矢命中で即死級 |
| 葬儀屋 -Mortician- | `mortician` | 20 | BONE | キル時に遺体位置にチェスト生成、周囲ドロップを格納 |
| 溶岩鶏 -LavaChicken- | `lavachicken` | 20 | LAVA_BUCKET | マグマバケツ×3 / 卵×10スタック / 恒常 SLOW_FALLING |
| 導矢 -Homing- | `homing` | 16 | ARROW | 発射した矢が重力無視で射手の視線方向に追従 (10秒) |
| 月詠 -Tsukuyomi- | `tsukuyomi` | 18 | PHANTOM_MEMBRANE | 0.75秒視線ロックで偽夜+BLIND+SLOW II (8秒)、追撃+3ダメ、常時 NIGHT_VISION (CD 45s) |
| 鏡像壁 -MirrorWall- | `mirrorwall` | 18 | TINTED_GLASS | 前方 2m に 3×3 の実 TINTED_GLASS、矢を完全遮断 (CD 30s) |
| 鉄槌 -Hammer- | `hammer` | 20 → 32 | MACE | 落下中に MACE で敵を殴るスラム命中で永続バフ (+2 MAX_HEALTH / +1 ATK) |

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
- **発動 (いずれかの条件を満たすと飛翔)**:
  - a) **フックがブロックに刺さった瞬間** (自動発動、明示的なリール操作不要)
  - b) **再右クリックでリール操作した瞬間** (フックが空中にあっても着地済みでも可)
- **能力**:
  - 疾風の足 — 試合中ずっと SPEED I (恒常)
  - 鉤縄 — フック位置へベクトル飛翔
  - 軽身 — 落下ダメージ無効
- **補足**:
  - 水中漁獲系 (BITE / CAUGHT_FISH / LURED) では発動しない (水辺での誤発動防止)
  - 至近距離 (< 0.5m) の発動は微量の前進 velocity のみ
  - 頭上 1〜2 ブロックが塞がっていれば Y 成分を 0.3 倍に抑制 (天井引っかかり回避)

### 衛生兵 -Medic-
- **id**: `medic`
- **HP**: 20
- **装備**: 石剣 / 革一式 / 金のりんご×2 / 医療ポーション×3 / パン×4
- **能力**: 応急処置 — 医療ポーションを空中で右クリックで即 8HP 回復 (1 本消費)

### 拳闘家 -Brawler-
- **id**: `brawler`
- **HP**: 22
- **装備**: Knockback II 木剣 / 釣り竿 / 革一式 / パン×4
- **能力**: 大男の拳 — KB II 木剣 + 追加 velocity の強力なノックバック

### 跳ね兎 -Kangaroo-
- **id**: `kangaroo`
- **HP**: 16
- **装備**: 石斧 / 革一式 / パン×4
- **能力**: 反重力 (恒常 JUMP BOOST II) / 羽根の着地 (落下ダメ完全無効)

### 圧殺者 -Stomper-
- **id**: `stomper`
- **HP**: 22
- **装備**: 鉄斧 / 鉄靴 / 革胴脚兜 / パン×4
- **能力**: 地響き — 着地地点半径 4m に敵がいるときのみ落下ダメ無効 + 敵へ落下距離分ダメージ (敵が近くにいない単独落下は通常)

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
  - 幻影 — シフト中 INVISIBILITY (装備は見える)
  - 死の宣告 — **透明解除後** に敵へ命中すると 30 秒の宣告、期限までに倒さないと自動処刑 (忍者のキル扱い)
  - 対象側 BossBar — 被宣告者には画面 2 行目に残時間カウントダウンが BossBar で表示
- **制約**:
  - 透明中の攻撃では宣告付与不可 (チャットで失敗通知)
  - 宣告後 15 秒は透明化ロック (シフトしても INVISIBILITY が付かない)
  - 宣告 CD 180 秒 (`IRON_SWORD` の Material cooldown + サイドバーに表示)

### 盾衛士 -Tank-
- **id**: `tank`
- **HP**: 30
- **装備**: 鉄胴 / 鉄兜 / チェーン脚靴 / 石剣 / パン×4
- **能力**: 鉄壁 (恒常 RESISTANCE I) / 代償: 鈍足 (恒常 SLOWNESS I)

### 雷神 -Thor-
- **id**: `thor`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 雷の杖 (Blaze Rod) / パン×4
- **能力**: 神鳴 — 杖を空中/ブロックに右クリで視線先 20〜35m に落雷
- **制約**: 距離外は失敗 (チャット通知、CD 付与なし) / CD 15秒 / 無敵時間中は不可

### バーサーカー -Berserker-
- **id**: `berserker`
- **HP**: 6 (開始) → 最大 40
- **装備**: Sharpness III 鉄剣 / 防具無し
- **能力**: 血戦 — キル毎に最大 HP +2 (上限 40) / 攻撃力 +0.5 (上限 +5)

### 吸血鬼 -Vampire-
- **id**: `vampire`
- **HP**: 20
- **装備**: チェーン一式 / 鉄剣 / パン×4
- **能力**: 陽光 (昼は被ダメ ×1.5) / 夜天 (夜は与ダメ ×1.5)。昼夜切替時に Title + SE 通知

### 波神 -Poseidon-
- **id**: `poseidon`
- **HP**: 18
- **装備**: 波神の銛 (Trident, Loyalty III + Impaling III + Unbreaking III) / 革一式 / パン×4
- **能力**: 忠義の銛 (Loyalty) / 潮騒 (水中・雨天で与ダメ ×1.5)

### 槍兵 -Lancer-
- **id**: `lancer`
- **HP**: 20
- **装備**: 穿孔の長槍 (`IRON_SPEAR` + Unbreaking III) / 鉄ヘルム / 鉄脚 / 鉄ブーツ / パン×4
- **能力**: 穿孔 (近接命中 +5) / 突撃 (スプリント中の命中で追加 +2)
- **補足**: 胴を空けた軽装寄せ構成

### 鎧武者 -Cuirassier-
- **id**: `cuirassier`
- **HP**: 24
- **装備**: 石剣 / 銘入り胴鎧 (Netherite Chestplate, Protection III + Unbreaking III) / パン×4
- **能力**: 鉄壁の胴 — 1 発 3.0 以上の被ダメを ×0.55 に軽減

### ストーカー -Tracker-
- **id**: `tracker`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 追跡のコンパス / パン×4
- **能力**: 追跡 — コンパス右クリで最寄り生存者の座標+距離をチャット表示 + 針同期
- **制約**: CD 5 秒 / 無敵時間中は不可

### スリ -Thief-
- **id**: `thief`
- **HP**: 18
- **装備**: 石剣 / 革一式 / 盗みの棒 (Blaze Rod) / パン×4
- **能力**: 拝借 — 対象プレイヤーに右クリで 27 スロット chest に相手の slot 9〜35 を複写、持ち出し分は相手から消える
- **制約**: 5m 超で自動クローズ / CD 10 秒 / chest への押込み不可 (一方通行) / 無敵時間中は不可

### トロール -Troll-
- **id**: `troll`
- **HP**: 18
- **装備**: KB II 木の棒 / 革一式 / パン×4
- **能力**: 大跳ね (KB II + 追加 velocity で約 6 マス) / 虹の歩 (足元をランダム色 WOOL に置換)

### 極 -LastManStanding-
- **id**: `lastmanstanding`
- **HP**: 2 (ハート 1)
- **装備**: なし (完全素手)
- **能力**: 一矢 — 弓矢命中で即死級ダメージ (cancel + 次 tick に 99999 ダメ)
- **特徴**: 装備・矢は現地で 1 から自作する覚悟が要る

### 葬儀屋 -Mortician-
- **id**: `mortician`
- **HP**: 20
- **装備**: 鉄剣 / 革一式 / パン×4
- **能力**: 遺品箱 — キル時に victim 位置にチェスト生成、半径 3m の Item entity を吸い込んで格納

### 溶岩鶏 -LavaChicken-
- **id**: `lavachicken`
- **HP**: 20
- **装備**: マグマバケツ×3 / 卵×10 スタック (各 16 個)
- **能力**: 羽根 (恒常 SLOW_FALLING) / 熔岩撒き (マグマバケツで足場溶岩化) / 弾幕 (卵を投げまくる)
- **補足**: Minecraft 映画『Lava Chicken』モチーフの変則型

### 導矢 -Homing-
- **id**: `homing`
- **HP**: 16
- **装備**: 素弓 / 木剣 / 矢×24 / 革一式 / パン×4
- **発動**: 弓を右クリで射撃
- **能力**: 導矢 — 発射した矢は **重力無視** + 毎 tick **射手の視線方向** に完全同期して velocity を更新
- **制約**: 発射速度 0.55 倍 / 追尾巡航 0.9 block/tick / ダメージ 0.5 倍 / ブロック接触か 10 秒で解除 / 視線追従 (敵ロック不要)

### 月詠 -Tsukuyomi-
- **id**: `tsukuyomi`
- **HP**: 18
- **装備**: Sharpness I 鉄剣 (§b月光の刃) / 革一式 / ファントムの膜 / 金のりんご / エンダーパール×1 / パン×4
- **発動**: 膜を空中で右クリでロック開始 → 0.75 秒視線中心に対象を捉え続けると発動
- **能力**:
  - 月読の瞳 — 常時 `NIGHT_VISION` (暗闇でも地形が見える)
  - 月詠 — 対象だけに偽の夜空 + `BLINDNESS` + `SLOWNESS II` を 8 秒
  - 月光の追撃 — BLINDNESS 状態の敵への近接ダメージ +3
- **制約**: 射程 30m / cos 0.92 視線中心 / ロック最長 4 秒でタイムアウト / CD 45 秒 / サイドバーに CD 表示

### 鏡像壁 -MirrorWall-
- **id**: `mirrorwall`
- **HP**: 18
- **装備**: 鉄剣 / 革一式 / 黒色ガラス / パン×4
- **能力**: 鏡像壁 — 前方 2m に 3×3 の TINTED_GLASS を **実ブロック** で設置。矢/トライデント等を完全遮断する物理的な壁
- **制約**: 設置先が空気でないと失敗 / 4 秒で自動消滅 (air に戻る) / CD 30 秒 / サイドバーに CD 表示

### 鉄槌 -Hammer-
- **id**: `hammer`
- **HP**: 20 (開始) → 最大 32 (キャップ)
- **装備**: 鉄槌 (MACE) / 鉄一式 / パン×4
- **発動**: 落下距離 **1.5 ブロック以上** の状態で敵を MACE で殴る (= スラム命中)
- **能力**:
  - バニラ MACE の追加ダメージ判定を利用 (落下距離に応じて大ダメージ)
  - スラム命中成立でさらに **永続バフ** を蓄積:
    - `MAX_HEALTH` +2 (上限 32)
    - `ATTACK_DAMAGE` +1 (上限 4 = +3 ボーナス)
- **制約**:
  - MACE 以外の武器ではバフは乗らない
  - 落下距離が足りない通常打撃では MACE のバニラ追加ダメージもバフ蓄積も発動しない
  - キャップ到達後は演出のみ
- **特徴**: 高所から飛び降りて叩きつける「重戦型」ビルド。試合が進むほど HP と攻撃力が伸びるスノーボール系

### 影分身 -Shadowclone- §8(封印中)
- **id**: `shadowclone`
- **状態**: `KitRegistry` で登録コメントアウト (Paper 26.1.2 対応版 ProtocolLib 待ち)
- クラス・リスナーは残置しているので、ProtocolLib 対応次第で 1 行復活で有効化可能

### 幻像 -Illusion- §8(封印中)
- **id**: `illusion`
- **状態**: Shadowclone と同じ理由で登録コメントアウト
- 現状の実装: 術者は装備を脱いで透明化 + 装備コピーした幻影が正面へ直線走行、敵が殴ると 3 ダメ反撃 + 幻影消滅 / 10 秒で自動終了

---

## カスタムレシピ

プラグインが登録する `ShapedRecipe` / `ShapelessRecipe`。`RecipeRegistry` で一括管理しプラグイン停止時に削除されます。

| レシピ ID | 型 | 材料 | 結果 |
|---|---|---|---|
| `hungergames:cheap_arrow` | Shaped | 火打ち石(上) + 棒(下) | 矢 ×2 |
| `hungergames:food_bowl_heal` | Shapeless | 食べ物 1 種 + 木の皿 (BOWL) | 民間治療薬 (HEALING Potion) |

`food_bowl_heal` の食べ物は `MaterialChoice` で列挙: BREAD / APPLE / 各種肉 (生・調理済み) / 魚 / 野菜 / 果実 / GOLDEN_APPLE / HONEY_BOTTLE など。

## MobLoot (動物ドロップ)

- 生肉を自動で焼肉版に置換 (`BEEF→COOKED_BEEF` 等)
- **動物 (`Animals` 系: 牛/豚/羊/鶏/ウサギ等) を倒すと 0〜2 本の糸を追加ドロップ** — バニラ弓 (STICK×3 + STRING×3) のクラフト材料
- モンスターは対象外

## 能力 CD のサイドバー表示

CD を持つ能力 (Thor / Ninja / Tracker / Thief / Tsukuyomi / MirrorWall) は **サイドバー「能力CD」欄** に残秒を常時表示。
`Kit.getCooldownAnchor()` で各能力が参照する `Material` を返し、`SidebarManager` が `p.getCooldown(anchor)` を監視して `§e X.Xs` / `§a READY` を表示する。
