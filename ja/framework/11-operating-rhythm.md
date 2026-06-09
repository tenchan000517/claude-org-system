# 運用の回転（ピースがどう組み合わさるか）

静的構造（役割・memory・ガバナンス）は骨格。これらの ritual が鼓動。
**価値は部品ではなくループにある**——各ピース単体は漏れる；組み合わさって初めて、地図・memory・handoff が
時間を通じて相互に一貫する。

## ループ

1. **Intake** — 新しい仕事/連絡がインボックスに入り、triage されて `INDEX` へ（`09-intake.md`）。
2. **Dispatch** — リーダーが `INDEX` 項目を作業員へ振る（`02-orchestration.md`）。
3. **Work** — 作業員が自分の dir で実行；知識は正しい家へ振り分けられる（`03-memory-model.md`）。
4. **Monitor** — スケジュールされた watcher が変化/イベントを intake/INDEX へ上げる（`10-monitoring.md`）。
5. **Finalize** — セッション終了時、**handoff-finalize** ritual が worklog＋HANDOFF＋memory＋秘書を
   **ドライラン検証つきで**更新し、次のターンが一貫状態を継承する（`templates/handoff-finalize.md`、`05-session-lifecycle.md`）。
6. → 1 へ戻る。

## 「組み合わせ」が肝心な理由

各 ritual 単体は漏れる：

- finalize 無き intake → 受理した仕事が綺麗に閉じない；状態がドリフト。
- intake 無き監視 → イベントが裏チャネルに発火し triage を迂回。
- 振り分け無き finalize → memory が誤った家に積もる（catch-all 回帰）。
- intake/monitor 無き work → 誰かがたまたま覚えてる事しか組織がやらない。

この回転が、構造を静的フォルダの集まりではなく*生きた*物にする。導入するチームは、テンプレを写すだけでなく
**ループを配線する**こと。

## ガバナンスはループの上に

方向性レベルの決定（`08-governance.md`）が、**intake が何を受理するか**と **monitor が何を見張るか**を形作る。
ある仕事ラインを止める決議は、intake がそれを断り、その monitor を退役させることを意味する。
ループは実行し、ガバナンスが操舵する。

## 規模の注記

1人運用は小さい版を回す：インボックスは短いリスト、監視は1〜2個のスケジュールチェック、finalize は5行の締め。
ループの*形*はどの規模でも同じです。
