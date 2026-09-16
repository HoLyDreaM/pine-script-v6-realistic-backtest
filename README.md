# Pine Script v6 Realistic Backtest

**Proje kökü:** `pine-script-v6-realistic-backtest/` (`d:\SoftWare\pine-script-v6-realistic-backtest`)

TradingView Pine Script **v6** için gerçekçi backtest örneği. Blog yazısı *“Pine Script v6 Backtest: 7 Adımda Gerçekçi Strateji Testi”* ile eşleşir.

Repo: [HoLyDreaM/pine-script-v6-realistic-backtest](https://github.com/HoLyDreaM/pine-script-v6-realistic-backtest)

## Dosyalar

| Dosya | Açıklama |
|-------|----------|
| `pine-script-v6-realistic-backtest.pine` | Strategy — komisyon, slippage, risk, repaint engeli |

## 7 adım → kod

| Adım | Uygulama |
|------|----------|
| 1 Execution model | `calc_on_every_tick=false`, `calc_on_order_fills=false`, kapalı mum sinyali |
| 2 Emir dolumu | `process_orders_on_close=false` → market emir sonraki bar açılışı |
| 3 Komisyon / slippage | `%0.075` komisyon + `2` tick slippage |
| 4 Repaint / lookahead | `barstate.isconfirmed` + `request.security(..., lookahead_off)` |
| 5 Risk / pozisyon | Equity % risk, ATR stop, R:R hedef |
| 6 Sağlamlık | Basit çift MA; yakın periyotlarla yeniden test edin |
| 7 Forward test | `alert` / `alertcondition` |

## Kurulum

1. TradingView → Pine Editor
2. `pine-script-v6-realistic-backtest.pine` içeriğini yapıştırın
3. **Add to chart** → Strategy Tester
4. Forward test: Alarm → **PS6-RBT Long / Short**

## Not

Bu örnek eğitim amaçlıdır; kârlılık garantisi vermez. Strategy Tester sonucunu komisyon, slippage, drawdown ve forward test ile birlikte yorumlayın.

## Lisans

Kod örnek olarak paylaşılmıştır; istediğiniz gibi uyarlayabilirsiniz.
