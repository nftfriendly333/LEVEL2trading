<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Guild Exchange — Live Order Book</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,600&family=JetBrains+Mono:wght@400;500;700&display=swap');

  :root{
    --bg:#0b0e13; --bg2:#0f131a; --panel:#131922; --panel2:#19212c;
    --line:#222b38; --line2:#2d3947; --txt:#e8ecf3; --muted:#828e9e; --muted2:#586575;
    --gold:#d8b45a; --gold-dim:#9c813b;
    --bid:#2bb673; --bid-soft:rgba(43,182,115,.16); --bid-line:rgba(43,182,115,.55);
    --ask:#e35a62; --ask-soft:rgba(227,90,98,.16); --ask-line:rgba(227,90,98,.55);
    --steel:#6ea8d8; --amber:#e0a64d;
    --mono:'JetBrains Mono',ui-monospace,SFMono-Regular,Menlo,monospace;
    --disp:'Fraunces',Georgia,'Times New Roman',serif;
    --ui:ui-sans-serif,-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;
  }
  *{box-sizing:border-box}
  html,body{margin:0;height:100%}
  body{
    background:
      radial-gradient(1200px 600px at 80% -10%, rgba(110,168,216,.05), transparent 60%),
      radial-gradient(900px 500px at -5% 110%, rgba(216,180,90,.05), transparent 55%),
      var(--bg);
    color:var(--txt); font-family:var(--ui); font-size:14px; line-height:1.4;
    -webkit-font-smoothing:antialiased;
  }
  .wrap{max-width:1320px;margin:0 auto;padding:16px 18px 40px}

  /* ---------- header ---------- */
  header{display:flex;align-items:center;gap:18px;flex-wrap:wrap;
    padding:10px 4px 16px;border-bottom:1px solid var(--line)}
  .brand{display:flex;flex-direction:column;line-height:1;margin-right:6px}
  .brand .mark{font-family:var(--disp);font-weight:600;font-size:23px;letter-spacing:.3px;
    color:var(--gold);display:flex;align-items:center;gap:9px}
  .brand .mark .crest{font-size:20px;filter:grayscale(.15)}
  .brand .sub{font-size:10.5px;letter-spacing:2.6px;text-transform:uppercase;color:var(--muted2);margin-top:6px;font-weight:600}

  .tabs{display:flex;gap:8px;margin-left:2px}
  .tab{display:flex;align-items:center;gap:10px;background:var(--panel);border:1px solid var(--line);
    border-radius:11px;padding:8px 13px;cursor:pointer;min-width:158px;transition:border-color .15s,background .15s}
  .tab:hover{border-color:var(--line2)}
  .tab.active{background:var(--panel2);border-color:var(--gold-dim)}
  .tab .ic{font-size:21px;line-height:1}
  .tab .nm{font-size:12px;color:var(--muted);font-weight:600;letter-spacing:.2px}
  .tab .px{font-family:var(--mono);font-size:16px;font-weight:700;letter-spacing:-.3px;margin-top:1px}
  .tab .chg{font-family:var(--mono);font-size:11px;font-weight:500}
  .up{color:var(--bid)} .down{color:var(--ask)} .flat{color:var(--muted)}

  .purse{margin-left:auto;display:flex;gap:22px;align-items:center}
  .stat{display:flex;flex-direction:column;align-items:flex-end;line-height:1.15}
  .stat .lbl{font-size:10px;text-transform:uppercase;letter-spacing:1.4px;color:var(--muted2);font-weight:600}
  .stat .val{font-family:var(--mono);font-size:17px;font-weight:700;margin-top:3px}
  .stat .val.gold{color:var(--gold)}
  .ghost-btn{background:transparent;border:1px solid var(--line2);color:var(--muted);
    font-family:var(--ui);font-size:12px;font-weight:600;padding:8px 12px;border-radius:9px;cursor:pointer;transition:.15s}
  .ghost-btn:hover{color:var(--txt);border-color:var(--gold-dim)}

  /* ---------- guide ---------- */
  .guide{margin:14px 0 0;background:linear-gradient(180deg,var(--panel),var(--bg2));
    border:1px solid var(--line);border-radius:14px;padding:16px 18px;display:none}
  .guide.open{display:block}
  .guide h3{margin:0 0 4px;font-family:var(--disp);font-weight:600;font-size:17px;color:var(--gold)}
  .guide p.intro{margin:0 0 14px;color:var(--muted);max-width:78ch}
  .guide-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:14px}
  .gcard{background:var(--bg2);border:1px solid var(--line);border-radius:10px;padding:12px 13px}
  .gcard h4{margin:0 0 5px;font-size:12px;letter-spacing:.3px;display:flex;align-items:center;gap:7px}
  .gcard .dot{width:9px;height:9px;border-radius:2px;display:inline-block}
  .gcard p{margin:0;color:var(--muted);font-size:12.5px;line-height:1.5}

  /* ---------- layout ---------- */
  .floor{display:grid;grid-template-columns:1.05fr 1fr 0.92fr;gap:14px;margin-top:16px;align-items:start}
  .card{background:var(--panel);border:1px solid var(--line);border-radius:14px;overflow:hidden}
  .card .head{display:flex;align-items:center;justify-content:space-between;
    padding:11px 14px;border-bottom:1px solid var(--line)}
  .card .head .t{font-size:11px;text-transform:uppercase;letter-spacing:1.6px;color:var(--muted);font-weight:700}
  .card .head .t b{color:var(--txt)}
  .card .head .hint{font-size:11px;color:var(--muted2);font-family:var(--mono)}

  /* ---------- order book ladder ---------- */
  .ladder{padding:6px 6px 10px}
  .colhdr{display:grid;grid-template-columns:1fr 1fr 1.5fr;gap:2px;padding:4px 10px 7px;
    font-size:10px;letter-spacing:1px;text-transform:uppercase;color:var(--muted2);font-weight:700}
  .colhdr span:nth-child(2){text-align:right}
  .colhdr span:nth-child(3){text-align:right}
  .row{position:relative;display:grid;grid-template-columns:1fr 1fr 1.5fr;gap:2px;
    align-items:center;padding:3px 10px;font-family:var(--mono);font-size:13px;border-radius:5px;
    min-height:25px}
  .row .bar{position:absolute;top:2px;bottom:2px;right:4px;border-radius:4px;z-index:0;width:0;
    transition:width .35s cubic-bezier(.2,.7,.3,1)}
  .row.ask .bar{background:var(--ask-soft)} .row.bid .bar{background:var(--bid-soft)}
  .row > *{position:relative;z-index:1}
  .row .price{font-weight:700}
  .row.ask .price{color:var(--ask)} .row.bid .price{color:var(--bid)}
  .row .size{text-align:right;color:var(--txt);opacity:.92}
  .row .cum{text-align:right;color:var(--muted2);font-size:11px}
  .row .you{position:absolute;left:-2px;top:50%;transform:translateY(-50%);z-index:2;
    background:var(--gold);color:#1a1408;font-family:var(--ui);font-weight:800;font-size:8.5px;
    letter-spacing:.5px;padding:2px 4px;border-radius:0 4px 4px 0;display:none}
  .row.mine .you{display:block}
  .row.mine{outline:1px solid rgba(216,180,90,.35);outline-offset:-1px}
  .row.best{background:rgba(255,255,255,.025)}
  .row.empty{opacity:.18}
  .row.empty .price,.row.empty .size,.row.empty .cum{visibility:hidden}
  @keyframes flashUp{0%{background:var(--bid-soft)}100%{background:transparent}}
  @keyframes flashDn{0%{background:var(--ask-soft)}100%{background:transparent}}
  .row.fup{animation:flashUp .5s ease-out} .row.fdn{animation:flashDn .5s ease-out}

  .spread{display:flex;align-items:center;justify-content:center;gap:14px;margin:5px 8px;
    padding:7px 10px;border-top:1px dashed var(--line2);border-bottom:1px dashed var(--line2)}
  .spread .last{font-family:var(--mono);font-size:20px;font-weight:700;display:flex;align-items:center;gap:6px}
  .spread .meta{font-family:var(--mono);font-size:11px;color:var(--muted)}
  .spread .meta b{color:var(--txt)}
  .arrow{font-size:13px}

  /* ---------- depth + tape ---------- */
  .stack{display:flex;flex-direction:column;gap:14px}
  .depthwrap{padding:10px 12px 12px}
  canvas{display:block;width:100%}
  .legend{display:flex;gap:16px;justify-content:center;margin-top:6px;font-size:11px;color:var(--muted)}
  .legend i{width:10px;height:10px;border-radius:2px;display:inline-block;margin-right:5px;vertical-align:-1px}
  .tape{max-height:188px;overflow:hidden;padding:4px 0}
  .trow{display:grid;grid-template-columns:1.1fr 1fr 1fr;gap:6px;padding:4px 14px;
    font-family:var(--mono);font-size:12.5px;align-items:center}
  .trow .tp{font-weight:700;display:flex;align-items:center;gap:5px}
  .trow .ts{text-align:right;color:var(--muted);opacity:.9}
  .trow .tt{text-align:right;color:var(--muted2);font-size:10.5px}
  @keyframes tapein{0%{opacity:0;transform:translateY(-5px)}100%{opacity:1;transform:none}}
  .trow.new{animation:tapein .4s ease-out}

  /* ---------- ticket ---------- */
  .ticket{padding:14px}
  .seg{display:grid;grid-template-columns:1fr 1fr;gap:6px;background:var(--bg2);
    border:1px solid var(--line);border-radius:11px;padding:5px;margin-bottom:11px}
  .seg button{border:0;background:transparent;color:var(--muted);font-family:var(--ui);
    font-weight:700;font-size:13.5px;padding:10px;border-radius:8px;cursor:pointer;transition:.13s;letter-spacing:.2px}
  .seg.bs button[data-on="buy"].on{background:var(--bid);color:#06160e}
  .seg.bs button[data-on="sell"].on{background:var(--ask);color:#1c0608}
  .seg.ty button.on{background:var(--panel2);color:var(--txt);box-shadow:inset 0 0 0 1px var(--line2)}

  .field{margin-bottom:11px}
  .field>label{display:flex;justify-content:space-between;align-items:center;
    font-size:11px;text-transform:uppercase;letter-spacing:.9px;color:var(--muted2);font-weight:700;margin-bottom:6px}
  .field>label .q{cursor:help;color:var(--muted2);border:1px solid var(--line2);border-radius:50%;
    width:15px;height:15px;display:inline-flex;align-items:center;justify-content:center;font-size:10px;font-weight:700}
  .stepper{display:grid;grid-template-columns:42px 1fr 42px;gap:6px}
  .stepper button{background:var(--bg2);border:1px solid var(--line2);color:var(--txt);
    font-size:18px;font-weight:700;border-radius:9px;cursor:pointer;line-height:1}
  .stepper button:hover{border-color:var(--gold-dim)}
  input.num{width:100%;background:var(--bg2);border:1px solid var(--line2);color:var(--txt);
    font-family:var(--mono);font-size:16px;font-weight:700;text-align:center;border-radius:9px;padding:9px;outline:none}
  input.num:focus{border-color:var(--gold)}
  .pxctl{display:grid;grid-template-columns:42px 1fr 42px;gap:6px}

  .est{background:var(--bg2);border:1px solid var(--line);border-radius:10px;padding:10px 12px;margin:4px 0 11px;
    display:flex;justify-content:space-between;align-items:baseline;font-size:12.5px;color:var(--muted)}
  .est b{font-family:var(--mono);font-size:15px;color:var(--txt);font-weight:700}
  .est .note{display:block;font-size:11px;color:var(--muted2);margin-top:3px}

  .place{width:100%;border:0;border-radius:11px;padding:13px;font-family:var(--ui);font-weight:800;
    font-size:15px;cursor:pointer;letter-spacing:.3px;transition:.13s;color:#fff}
  .place.buy{background:linear-gradient(180deg,#2fc47e,#23995f);color:#04140c}
  .place.sell{background:linear-gradient(180deg,#ec656d,#cf4750);color:#1c0507}
  .place:hover{filter:brightness(1.07)}
  .place:active{transform:translateY(1px)}
  .msg{min-height:17px;margin-top:9px;font-size:12px;text-align:center;font-weight:600}
  .msg.ok{color:var(--bid)} .msg.err{color:var(--ask)} .msg.info{color:var(--gold)}

  .holdings{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin:14px 0 4px}
  .hold{background:var(--bg2);border:1px solid var(--line);border-radius:10px;padding:9px 11px}
  .hold .hl{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--muted2);font-weight:700}
  .hold .hv{font-family:var(--mono);font-size:16px;font-weight:700;margin-top:3px;display:flex;align-items:center;gap:6px}
  .hold .hv small{color:var(--muted);font-size:11px;font-weight:500}

  .orders .head{padding-bottom:9px}
  .ordlist{padding:6px 8px 10px;display:flex;flex-direction:column;gap:6px;min-height:40px}
  .ord{display:grid;grid-template-columns:auto 1fr auto auto;gap:8px;align-items:center;
    background:var(--bg2);border:1px solid var(--line);border-radius:9px;padding:7px 10px;font-family:var(--mono);font-size:12.5px}
  .ord .tag{font-family:var(--ui);font-weight:800;font-size:9.5px;letter-spacing:.5px;padding:3px 6px;border-radius:5px}
  .ord .tag.b{background:var(--bid-soft);color:var(--bid)} .ord .tag.s{background:var(--ask-soft);color:var(--ask)}
  .ord .od{color:var(--muted)}
  .ord .op{font-weight:700}
  .ord .cancel{background:transparent;border:1px solid var(--line2);color:var(--muted);border-radius:6px;
    padding:4px 8px;font-size:11px;cursor:pointer;font-family:var(--ui);font-weight:600}
  .ord .cancel:hover{color:var(--ask);border-color:var(--ask)}
  .ordempty{color:var(--muted2);font-size:12px;text-align:center;padding:12px 0;font-style:italic}

  @media (max-width:1080px){.floor{grid-template-columns:1fr 1fr}.ticketcard{grid-column:1/-1}}
  @media (max-width:720px){
    .floor{grid-template-columns:1fr}.purse{width:100%;margin:8px 0 0;justify-content:space-between}
    .tabs{width:100%}.tab{flex:1;min-width:0}
  }
  @media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}
  .footnote{margin-top:22px;text-align:center;color:var(--muted2);font-size:11px}

  /* ---------- learn-to-trade modal ---------- */
  .learn-btn{border-color:var(--gold-dim);color:var(--gold)}
  .learn-btn:hover{background:rgba(216,180,90,.1);color:var(--gold);border-color:var(--gold)}
  .modal-back{position:fixed;inset:0;background:rgba(6,8,12,.74);backdrop-filter:blur(3px);
    display:none;align-items:center;justify-content:center;z-index:50;padding:20px}
  .modal-back.open{display:flex}
  .modal{background:linear-gradient(180deg,var(--panel),var(--bg2));border:1px solid var(--line2);
    border-radius:16px;width:min(780px,100%);max-height:90vh;display:flex;flex-direction:column;
    box-shadow:0 30px 80px rgba(0,0,0,.55);overflow:hidden}
  .modal-head{display:flex;align-items:center;justify-content:space-between;padding:16px 20px;border-bottom:1px solid var(--line)}
  .modal-head h2{margin:0;font-family:var(--disp);font-weight:600;font-size:20px;color:var(--gold);display:flex;gap:9px;align-items:center}
  .modal-head .x{background:transparent;border:1px solid var(--line2);color:var(--muted);width:32px;height:32px;
    border-radius:9px;cursor:pointer;font-size:14px}
  .modal-head .x:hover{color:var(--txt);border-color:var(--gold-dim)}
  .ltabs{display:flex;gap:6px;padding:13px 20px 0}
  .ltab{background:transparent;border:1px solid var(--line);border-bottom:0;color:var(--muted);
    font-family:var(--ui);font-weight:700;font-size:13px;padding:9px 15px;border-radius:9px 9px 0 0;cursor:pointer}
  .ltab.on{background:var(--panel2);color:var(--txt);border-color:var(--line2)}
  .lbody{padding:18px 20px 22px;overflow:auto}
  .lintro{color:var(--muted);margin:0 0 16px;max-width:72ch;line-height:1.55}
  .lintro b{color:var(--txt)}

  .dwrap{display:grid;grid-template-columns:minmax(210px,1fr) 1.15fr;gap:18px;align-items:start}
  @media(max-width:580px){.dwrap{grid-template-columns:1fr}}
  .dbook{background:var(--bg2);border:1px solid var(--line);border-radius:11px;padding:8px 8px 10px}
  .dcap{font-size:10px;text-transform:uppercase;letter-spacing:1.2px;color:var(--muted2);font-weight:700;padding:4px 8px 8px}
  .drow{position:relative;display:grid;grid-template-columns:1fr 1fr;gap:4px;align-items:center;padding:5px 10px;
    font-family:var(--mono);font-size:13.5px;border-radius:5px;min-height:27px}
  .drow .dbar{position:absolute;top:2px;bottom:2px;right:4px;border-radius:4px;z-index:0;transition:width .4s ease}
  .drow.ask .dbar{background:var(--ask-soft)} .drow.bid .dbar{background:var(--bid-soft)}
  .drow>*{position:relative;z-index:1}
  .drow .dp{font-weight:700} .drow.ask .dp{color:var(--ask)} .drow.bid .dp{color:var(--bid)}
  .drow .ds{text-align:right;opacity:.92}
  .drow.hit{outline:2px solid var(--gold);outline-offset:-2px;background:rgba(216,180,90,.13)}
  .drow .take{position:absolute;right:9px;top:50%;transform:translateY(-50%);z-index:2;font-family:var(--ui);
    font-weight:800;font-size:10px;color:var(--gold)}
  .drow .dyou{position:absolute;left:-2px;top:50%;transform:translateY(-50%);z-index:2;background:var(--gold);
    color:#1a1408;font-family:var(--ui);font-weight:800;font-size:8.5px;padding:2px 5px;border-radius:0 4px 4px 0}
  .drow.mine{outline:1px solid rgba(216,180,90,.5);outline-offset:-1px}
  .dspread{display:flex;justify-content:center;gap:12px;font-family:var(--mono);font-size:11px;color:var(--muted);
    margin:5px 6px;padding:5px;border-top:1px dashed var(--line2);border-bottom:1px dashed var(--line2)}
  .dspread b{color:var(--txt)}

  .lside{display:flex;flex-direction:column;gap:12px}
  .lbtns{display:flex;flex-wrap:wrap;gap:8px}
  .lbtn{flex:1;min-width:152px;border:1px solid var(--line2);border-radius:10px;padding:11px 12px;cursor:pointer;
    font-family:var(--ui);font-weight:700;font-size:13px;background:var(--bg2);color:var(--txt);text-align:left;transition:.13s}
  .lbtn small{display:block;font-weight:500;color:var(--muted);font-size:11px;margin-top:3px}
  .lbtn.market{border-color:rgba(110,168,216,.55)} .lbtn.market:hover{background:rgba(110,168,216,.1)}
  .lbtn.limit{border-color:rgba(224,166,77,.55)} .lbtn.limit:hover{background:rgba(224,166,77,.1)}
  .lbtn.reset{flex:0 0 auto;border-color:var(--line);color:var(--muted);font-weight:600}
  .lbtn.reset:hover{color:var(--txt);border-color:var(--gold-dim)}

  .result{background:var(--bg2);border:1px solid var(--line);border-radius:11px;padding:14px;min-height:118px}
  .result .rt{font-weight:800;font-size:14px;margin:0 0 9px;display:flex;align-items:center;gap:8px;flex-wrap:wrap}
  .result .legs{font-family:var(--mono);font-size:12.5px;color:var(--muted);margin:0 0 10px;line-height:1.7}
  .result p{margin:0;color:var(--muted);font-size:12.5px;line-height:1.55}
  .result .big{font-family:var(--mono);font-weight:700;color:var(--txt)}
  .result b{color:var(--txt)}
  .verdict{display:inline-flex;align-items:center;gap:5px;font-weight:800;font-size:11px;letter-spacing:.4px;
    padding:4px 9px;border-radius:6px;text-transform:uppercase}
  .verdict.good{background:var(--bid-soft);color:var(--bid)} .verdict.bad{background:var(--ask-soft);color:var(--ask)}
  .takeaway{background:rgba(216,180,90,.08);border:1px solid rgba(216,180,90,.25);border-radius:9px;padding:10px 12px;
    font-size:12.5px;color:var(--txt);margin-top:12px;line-height:1.5}
  .takeaway b{color:var(--gold)}
  .chips{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:16px}
  .chip{border:1px solid var(--line2);background:var(--bg2);color:var(--muted);border-radius:20px;padding:7px 13px;
    font-family:var(--ui);font-weight:700;font-size:12.5px;cursor:pointer;display:flex;align-items:center;gap:7px;transition:.13s}
  .chip .pip{width:8px;height:8px;border-radius:50%}
  .chip.good .pip{background:var(--bid)} .chip.bad .pip{background:var(--ask)}
  .chip.on{color:var(--txt);border-color:var(--gold-dim);background:var(--panel2)}
</style>
</head>
<body>
<div class="wrap">
  <header>
    <div class="brand">
      <div class="mark"><span class="crest">⚖️</span>Guild Exchange</div>
      <div class="sub">Player&nbsp;vs&nbsp;Market · Level&nbsp;2 Order&nbsp;Book</div>
    </div>

    <div class="tabs" id="tabs"></div>

    <div class="purse">
      <div class="stat"><span class="lbl">Purse</span><span class="val gold" id="goldVal">10,000g</span></div>
      <div class="stat"><span class="lbl">Net worth</span><span class="val" id="netVal">—</span></div>
      <div class="stat"><span class="lbl">Session P&L</span><span class="val" id="pnlVal">+0g</span></div>
      <button class="ghost-btn" id="guideBtn">How to read this</button>
      <button class="ghost-btn learn-btn" id="learnBtn">Learn to trade</button>
      <button class="ghost-btn" id="resetBtn">Reset</button>
    </div>
  </header>

  <section class="guide" id="guide">
    <h3>The basics</h3>
    <p class="intro">You trade against the market, not other players. Prices move on their own. Try to buy low and sell high — it's all practice gold.</p>
    <div class="guide-grid">
      <div class="gcard"><h4><span class="dot" style="background:var(--ask)"></span>Asks (red)</h4><p>People selling. The lowest one is the cheapest to buy.</p></div>
      <div class="gcard"><h4><span class="dot" style="background:var(--bid)"></span>Bids (green)</h4><p>People buying. The highest one is the best price to sell.</p></div>
      <div class="gcard"><h4><span class="dot" style="background:var(--gold)"></span>Spread</h4><p>The gap between them. Smaller gap = easier to trade.</p></div>
      <div class="gcard"><h4><span class="dot" style="background:var(--steel)"></span>Market order</h4><p>Buy or sell right now. Fast, but costs a bit more.</p></div>
      <div class="gcard"><h4><span class="dot" style="background:var(--amber)"></span>Limit order</h4><p>Pick your price and wait. Cheaper, but may not happen.</p></div>
      <div class="gcard"><h4><span class="dot" style="background:var(--gold)"></span>Depth chart</h4><p>Shows how many buyers and sellers are lined up.</p></div>
    </div>
  </section>

  <section class="floor">
    <!-- ORDER BOOK -->
    <div class="card">
      <div class="head">
        <div class="t">Level 2 — <b id="bookName">Basic Sword</b></div>
        <div class="hint" id="bookHint">live</div>
      </div>
      <div class="ladder">
        <div class="colhdr"><span>Price (g)</span><span>Size</span><span>Total</span></div>
        <div id="askRows"></div>
        <div class="spread">
          <div class="last" id="lastPx">—</div>
          <div class="meta">spread <b id="spreadVal">—</b> · mid <b id="midVal">—</b></div>
        </div>
        <div id="bidRows"></div>
      </div>
    </div>

    <!-- DEPTH + TAPE -->
    <div class="stack">
      <div class="card">
        <div class="head"><div class="t">Market depth</div><div class="hint">cumulative size</div></div>
        <div class="depthwrap">
          <canvas id="depth" height="190"></canvas>
          <div class="legend"><span><i style="background:var(--bid)"></i>Buyers (bids)</span><span><i style="background:var(--ask)"></i>Sellers (asks)</span></div>
        </div>
      </div>
      <div class="card">
        <div class="head"><div class="t">Recent trades</div><div class="hint">price · size</div></div>
        <div class="tape" id="tape"></div>
      </div>
    </div>

    <!-- TICKET -->
    <div class="card ticketcard">
      <div class="head"><div class="t">Trade ticket</div><div class="hint" id="ticketHint">⚔ Basic Sword</div></div>
      <div class="ticket">
        <div class="seg bs" id="segBS">
          <button data-on="buy" class="on">Buy</button>
          <button data-on="sell">Sell</button>
        </div>
        <div class="seg ty" id="segTY">
          <button data-on="market" class="on">Market</button>
          <button data-on="limit">Limit</button>
        </div>

        <div class="field">
          <label>Quantity <span class="q" title="How many units to trade.">?</span></label>
          <div class="stepper">
            <button id="qDn">−</button>
            <input class="num" id="qty" inputmode="numeric" value="1">
            <button id="qUp">+</button>
          </div>
        </div>

        <div class="field" id="priceField" style="display:none">
          <label>Limit price (g) <span class="q" title="Your order rests in the book at this price until a guild trades into it.">?</span></label>
          <div class="pxctl">
            <button id="pDn">−</button>
            <input class="num" id="price" inputmode="decimal" value="">
            <button id="pUp">+</button>
          </div>
        </div>

        <div class="est" id="est"><span id="estLbl">Est. cost</span><span style="text-align:right"><b id="estVal">—</b><span class="note" id="estNote"></span></span></div>

        <button class="place buy" id="place">Buy ⚔ Sword</button>
        <div class="msg" id="msg"></div>

        <div class="holdings">
          <div class="hold"><div class="hl">⚔ Swords</div><div class="hv" id="hSword">0 <small></small></div></div>
          <div class="hold"><div class="hl">🛡 Shields</div><div class="hv" id="hShield">0 <small></small></div></div>
        </div>
      </div>
      <div class="orders">
        <div class="head"><div class="t">Your open orders <b id="ordCount"></b></div><div class="hint">resting</div></div>
        <div class="ordlist" id="ordList"></div>
      </div>
    </div>
  </section>

  <div class="modal-back" id="lessonBack">
    <div class="modal" role="dialog" aria-modal="true" aria-label="Learn to trade">
      <div class="modal-head">
        <h2><span>🎓</span>Learn to trade</h2>
        <button class="x" id="lessonClose" aria-label="Close lessons">✕</button>
      </div>
      <div class="ltabs">
        <button class="ltab on" data-tab="ml">Market vs Limit</button>
        <button class="ltab" data-tab="gb">Good vs bad trades</button>
      </div>
      <div class="lbody" id="lessonBody"></div>
    </div>
  </div>

  <p class="footnote">A practice sandbox · no real currency · prices simulated by market-maker guilds</p>
</div>

<script>
"use strict";
/* ============================================================
   Guild Exchange — PvE Level 2 order book simulator
   ============================================================ */

const ITEMS = {
  sword:  { key:'sword',  name:'Basic Sword',  icon:'⚔', tick:0.1, fair:12.0, vol:0.10, accent:'var(--amber)' },
  shield: { key:'shield', name:'Basic Shield', icon:'🛡', tick:0.1, fair:8.0,  vol:0.08, accent:'var(--steel)' },
};
const VIEW_LEVELS = 8;       // ladder slots per side
const START_GOLD = 10000;
const START_INV  = { sword:3, shield:2 };

let SEQ = 1;                 // global order sequence (price-time priority)
let ORD = 1;                 // user order id
const markets = {};
let active = 'sword';

const player = {
  gold: START_GOLD,
  reservedGold: 0,
  inv: { sword:{qty:START_INV.sword,reserved:0}, shield:{qty:START_INV.shield,reserved:0} },
  startNet: 0,
};

// ticket state
const ticket = { side:'buy', type:'market' };

/* ---------- helpers ---------- */
const rnd  = (a,b)=>a+Math.random()*(b-a);
const irnd = (a,b)=>Math.floor(rnd(a,b+1));
const gauss= ()=> (Math.random()+Math.random()+Math.random()+Math.random()-2)/1.4;
const roundTick=(p,t)=>Math.max(t, Math.round(p/t)*t);
const fmtG = g => Math.round(g).toLocaleString('en-US');
const fmtP = p => p.toFixed(1);
const bestBid = m => m.bids[0] ? m.bids[0].price : null;
const bestAsk = m => m.asks[0] ? m.asks[0].price : null;
const mid = m => { const b=bestBid(m),a=bestAsk(m); if(b!=null&&a!=null)return (a+b)/2; return m.last??ITEMS[m.key].fair; };

/* ---------- build markets ---------- */
function newMarket(key){
  const cfg = ITEMS[key];
  const m = { key, fair:cfg.fair, tick:cfg.tick, bids:[], asks:[], last:cfg.fair, prevLast:cfg.fair,
              open:cfg.fair, trades:[], hist:[] };
  // seed depth
  for(let i=1;i<=VIEW_LEVELS;i++){
    addLimit(m,'bid', roundTick(cfg.fair - i*cfg.tick, cfg.tick), irnd(2,9),'env');
    addLimit(m,'ask', roundTick(cfg.fair + i*cfg.tick, cfg.tick), irnd(2,9),'env');
  }
  sortBook(m);
  for(let i=0;i<60;i++) m.hist.push(cfg.fair);
  return m;
}
function sortBook(m){
  m.bids.sort((x,y)=> y.price-x.price || x.seq-y.seq);
  m.asks.sort((x,y)=> x.price-y.price || x.seq-y.seq);
}
function levelAt(book, price){ return book.find(o=>Math.abs(o.price-price)<1e-6); }

function addLimit(m, side, price, size, owner, id){
  if(size<=0) return null;
  price = roundTick(price, m.tick);
  const book = side==='bid'? m.bids : m.asks;
  // env: never cross
  if(owner==='env'){
    if(side==='bid' && bestAsk(m)!=null && price>=bestAsk(m)) return null;
    if(side==='ask' && bestBid(m)!=null && price<=bestBid(m)) return null;
  }
  // merge same price + same owner-class for env; user orders kept distinct
  if(owner==='env'){
    const ex = book.find(o=>o.owner==='env' && Math.abs(o.price-price)<1e-6);
    if(ex){ ex.size=Math.min(ex.size+size, 18); return ex; } // cap so the ladder stays readable
  }
  const o = { id: id??('e'+SEQ), price, size, owner, seq:SEQ++, side };
  book.push(o);
  return o;
}

/* ---------- matching: take liquidity ---------- */
// side: 'buy' eats asks, 'sell' eats bids. owner: who is the taker.
function takeLiquidity(m, side, qty, opts={}){
  const owner = opts.owner||'env';
  const maxPrice = opts.maxPrice; // for user marketable limits
  const book = side==='buy'? m.asks : m.bids;
  let remaining = qty, filled=0, spend=0;
  while(remaining>0 && book.length){
    const lvl = book[0];
    if(maxPrice!=null){
      if(side==='buy' && lvl.price>maxPrice+1e-9) break;
      if(side==='sell'&& lvl.price<maxPrice-1e-9) break;
    }
    if(owner==='you' && lvl.owner==='you') break; // no self-trade
    let t = Math.min(lvl.size, remaining);
    if(owner==='you'){
      if(side==='buy'){ const aff=Math.floor((player.gold+1e-9)/lvl.price); t=Math.min(t,aff); }
      else { const avail=player.inv[m.key].qty-player.inv[m.key].reserved; t=Math.min(t,avail); }
      if(t<=0) break;
    }
    const px=lvl.price;
    // taker side accounting (only when the user is the taker)
    if(owner==='you'){
      if(side==='buy'){ player.gold-=t*px; player.inv[m.key].qty+=t; }
      else { player.inv[m.key].qty-=t; player.gold+=t*px; }
    }
    // maker side accounting (only when a resting USER order gets hit)
    if(lvl.owner==='you'){
      if(side==='buy'){ // taker buys from user's ask => user SOLD
        player.inv[m.key].reserved-=t; player.inv[m.key].qty-=t; player.gold+=t*px;
        flash(`Filled: sold ${t} ${ITEMS[m.key].icon} @ ${fmtP(px)}g`,'ok');
      } else {           // taker sells into user's bid => user BOUGHT
        const L=lvl.price; player.reservedGold-=t*L; player.gold+=t*(L-px); player.inv[m.key].qty+=t;
        flash(`Filled: bought ${t} ${ITEMS[m.key].icon} @ ${fmtP(px)}g`,'ok');
      }
    }
    lvl.size-=t; remaining-=t; filled+=t; spend+=t*px;
    if(lvl.size<=1e-9) book.shift();
    recordTrade(m, px, t, side);
  }
  return { filled, spend };
}

function recordTrade(m, price, size, takerSide){
  m.prevLast=m.last; m.last=price;
  m.trades.unshift({ price, size, side:takerSide, t:Date.now(), fresh:true });
  if(m.trades.length>40) m.trades.pop();
}

/* ---------- simulation tick ---------- */
function simTick(){
  for(const key in markets) stepMarket(markets[key]);
  renderAll();
}
function stepMarket(m){
  const cfg=ITEMS[m.key];
  // 1) fair value random walk
  m.fair = Math.max(2, m.fair + gauss()*cfg.vol);
  // 2) churn: pull a few far env orders
  if(Math.random()<0.75) pullEnv(m, m.bids);
  if(Math.random()<0.75) pullEnv(m, m.asks);
  // 3) replenish env liquidity around fair (small top-ups; cap keeps it realistic)
  const want=VIEW_LEVELS;
  for(let i=1;i<=want;i++){
    if(Math.random()<0.35) addLimit(m,'bid', m.fair - i*m.tick - rnd(0,m.tick), irnd(1,5),'env');
    if(Math.random()<0.35) addLimit(m,'ask', m.fair + i*m.tick + rnd(0,m.tick), irnd(1,5),'env');
  }
  // ensure minimum depth
  ensureDepth(m,'bid'); ensureDepth(m,'ask');
  trimBook(m);
  sortBook(m);
  // 4) env aggressor crosses spread -> trades
  if(Math.random()<0.72){
    const buy = Math.random() < 0.5 + (m.fair-mid(m))*0.12; // lean toward fair
    takeLiquidity(m, buy?'buy':'sell', irnd(1,4), {owner:'env'});
    sortBook(m);
  }
  // keep books from drifting locked
  uncross(m);
  m.hist.push(mid(m)); if(m.hist.length>90) m.hist.shift();
}
function pullEnv(m, book){
  const envs = book.filter(o=>o.owner==='env');
  if(envs.length<=3) return;
  const victim = envs[irnd(Math.floor(envs.length/2), envs.length-1)]; // bias to far levels
  const i=book.indexOf(victim);
  if(i>=0){ victim.size-=irnd(1,Math.max(1,Math.ceil(victim.size/2))); if(victim.size<=0) book.splice(i,1); }
}
function ensureDepth(m, side){
  const book = side==='bid'? m.bids : m.asks;
  let guard=0;
  while(book.length<6 && guard++<12){
    const k=book.length+1;
    addLimit(m, side, side==='bid'? m.fair-k*m.tick : m.fair+k*m.tick, irnd(2,8),'env');
    sortBook(m);
  }
}
function trimBook(m){
  if(m.bids.length>VIEW_LEVELS+3) m.bids.length=VIEW_LEVELS+3;
  if(m.asks.length>VIEW_LEVELS+3) m.asks.length=VIEW_LEVELS+3;
}
function uncross(m){
  let guard=0;
  while(bestBid(m)!=null && bestAsk(m)!=null && bestBid(m)>=bestAsk(m) && guard++<20){
    // resolve by trading the smaller env side away (skip user orders to keep their resting fills meaningful)
    const b=m.bids[0], a=m.asks[0];
    if(b.owner==='you' && a.owner==='you'){ break; }
    if(b.owner==='env'){ b.size-=1; if(b.size<=0) m.bids.shift(); }
    else { a.size-=1; if(a.size<=0) m.asks.shift(); }
  }
}

/* ---------- user actions ---------- */
function placeOrder(){
  const m=markets[active];
  const qty=Math.max(1, Math.round(Number(document.getElementById('qty').value)||0));
  const side=ticket.side, type=ticket.type;
  clearMsg();

  if(type==='market'){
    if(side==='buy'){
      if(!m.asks.length) return flash('No sellers to buy from right now.','err');
      if(player.gold < bestAsk(m)) return flash('Not enough gold to buy a single unit.','err');
      const r=takeLiquidity(m,'buy',qty,{owner:'you'});
      if(r.filled===0) flash('Couldn\'t fill — out of gold.','err');
      else flash(`Bought ${r.filled} ${ITEMS[m.key].icon} for ${fmtG(r.spend)}g (avg ${fmtP(r.spend/r.filled)}).`,'ok');
    } else {
      const avail=player.inv[m.key].qty-player.inv[m.key].reserved;
      if(avail<=0) return flash(`You have no ${ITEMS[m.key].name.toLowerCase()}s available to sell.`,'err');
      if(!m.bids.length) return flash('No buyers in the book right now.','err');
      const r=takeLiquidity(m,'sell',Math.min(qty,avail),{owner:'you'});
      flash(`Sold ${r.filled} ${ITEMS[m.key].icon} for ${fmtG(r.spend)}g (avg ${fmtP(r.spend/r.filled)}).`,'ok');
    }
  } else { // limit
    let price=roundTick(Number(document.getElementById('price').value)||0, m.tick);
    if(price<=0) return flash('Enter a valid limit price.','err');
    if(side==='buy'){
      const r=takeLiquidity(m,'buy',qty,{owner:'you',maxPrice:price});
      let rest=qty-r.filled;
      // only rest non-marketable remainder (price below best ask)
      const canRest = rest>0 && (!m.asks.length || price < bestAsk(m));
      if(canRest){
        const need=rest*price;
        const affordable=Math.min(rest, Math.floor((player.gold+1e-9)/price));
        if(affordable>0){
          player.gold-=affordable*price; player.reservedGold+=affordable*price;
          addLimit(m,'bid',price,affordable,'you','u'+(ORD++));
        }
        const filledMsg = r.filled? `Bought ${r.filled} now; ` : '';
        if(affordable>0) flash(`${filledMsg}resting buy ${affordable} @ ${fmtP(price)}g in the book.`,'info');
        else if(r.filled) flash(`Bought ${r.filled} ${ITEMS[m.key].icon}; not enough gold to rest more.`,'ok');
        else flash('Not enough gold to place that order.','err');
      } else if(r.filled){
        flash(`Bought ${r.filled} ${ITEMS[m.key].icon} for ${fmtG(r.spend)}g.`,'ok');
      } else {
        flash('Not enough gold to fill at that price.','err');
      }
    } else {
      const r=takeLiquidity(m,'sell',qty,{owner:'you',maxPrice:price});
      let rest=qty-r.filled;
      const availNow=player.inv[m.key].qty-player.inv[m.key].reserved;
      const canRest = rest>0 && availNow>0 && (!m.bids.length || price > bestBid(m));
      if(canRest){
        const r2=Math.min(rest,availNow);
        player.inv[m.key].reserved+=r2;
        addLimit(m,'ask',price,r2,'you','u'+(ORD++));
        const filledMsg = r.filled? `Sold ${r.filled} now; ` : '';
        flash(`${filledMsg}resting sell ${r2} @ ${fmtP(price)}g in the book.`,'info');
      } else if(r.filled){
        flash(`Sold ${r.filled} ${ITEMS[m.key].icon} for ${fmtG(r.spend)}g.`,'ok');
      } else {
        flash(availNow<=0? 'No units available to sell.' : 'Order didn\'t rest — price too low.','err');
      }
    }
  }
  sortBook(m); renderAll(); syncTicket();
}

function cancelOrder(m, id){
  const b=m.bids.find(o=>o.id===id), a=m.asks.find(o=>o.id===id);
  const o=b||a;
  if(!o) return;
  if(o.side==='bid'){ player.reservedGold-=o.size*o.price; player.gold+=o.size*o.price; m.bids.splice(m.bids.indexOf(o),1); }
  else { player.inv[m.key].reserved-=o.size; m.asks.splice(m.asks.indexOf(o),1); }
  flash('Order cancelled.','info'); renderAll(); syncTicket();
}

/* ---------- net worth / P&L ---------- */
function netWorth(){
  let n=player.gold+player.reservedGold;
  for(const k in player.inv) n += player.inv[k].qty * mid(markets[k]);
  return n;
}

/* ============================================================
   RENDERING
   ============================================================ */
function renderAll(){ renderTabs(); renderPurse(); renderBook(); renderDepth(); renderTape(); renderHoldings(); renderOrders(); }

function renderTabs(){
  const el=document.getElementById('tabs');
  if(!el.dataset.built){
    el.innerHTML=Object.values(ITEMS).map(it=>`
      <div class="tab ${it.key===active?'active':''}" data-k="${it.key}">
        <span class="ic">${it.icon}</span>
        <div><div class="nm">${it.name}</div>
        <div class="px" id="tabPx-${it.key}">—</div>
        <div class="chg" id="tabChg-${it.key}">—</div></div>
      </div>`).join('');
    el.dataset.built='1';
    el.querySelectorAll('.tab').forEach(t=>t.onclick=()=>{ active=t.dataset.k; el.querySelectorAll('.tab').forEach(x=>x.classList.toggle('active',x.dataset.k===active)); resetTicketDefaults(); renderAll(); });
  } else {
    el.querySelectorAll('.tab').forEach(x=>x.classList.toggle('active',x.dataset.k===active));
  }
  for(const k in markets){
    const m=markets[k]; const px=document.getElementById('tabPx-'+k); const ch=document.getElementById('tabChg-'+k);
    px.textContent=fmtP(m.last)+'g';
    const d=m.last-m.open; const cls=d>0.0001?'up':d<-0.0001?'down':'flat';
    px.className='px '+cls; ch.className='chg '+cls;
    ch.textContent=(d>=0?'▲ +':'▼ ')+fmtP(Math.abs(d))+' ('+(d>=0?'+':'-')+Math.abs(d/m.open*100).toFixed(1)+'%)';
  }
}

function renderPurse(){
  document.getElementById('goldVal').textContent=fmtG(player.gold)+'g';
  const net=netWorth();
  document.getElementById('netVal').textContent=fmtG(net)+'g';
  const pnl=net-player.startNet;
  const pe=document.getElementById('pnlVal');
  pe.textContent=(pnl>=0?'+':'−')+fmtG(Math.abs(pnl))+'g';
  pe.className='val '+(pnl>0.5?'up':pnl<-0.5?'down':'flat');
}

const prevSizes={bid:{},ask:{}};
function renderBook(){
  const m=markets[active];
  document.getElementById('bookName').textContent=ITEMS[m.key].name;

  const asks=m.asks.slice(0,VIEW_LEVELS);   // best..worse
  const bids=m.bids.slice(0,VIEW_LEVELS);
  const maxSize=Math.max(1, ...asks.map(o=>o.size), ...bids.map(o=>o.size));

  // asks: render worst at top, best (nearest spread) at bottom
  let cum=0; const askCum=[];
  for(const o of asks){ cum+=o.size; askCum.push(cum); }
  const askHtml=[];
  for(let slot=VIEW_LEVELS-1; slot>=0; slot--){
    const o=asks[slot];
    askHtml.push(rowHtml('ask', o, o?askCum[slot]:0, maxSize, slot===0));
  }
  document.getElementById('askRows').innerHTML=askHtml.join('');

  // bids: best at top
  cum=0;
  const bidHtml=bids.map((o,i)=>{ cum+=o.size; return rowHtml('bid',o,cum,maxSize,i===0); });
  while(bidHtml.length<VIEW_LEVELS) bidHtml.push(rowHtml('bid',null,0,maxSize,false));
  document.getElementById('bidRows').innerHTML=bidHtml.join('');

  // spread / last
  const b=bestBid(m),a=bestAsk(m);
  const lastEl=document.getElementById('lastPx');
  const dir=m.last>m.prevLast?'up':m.last<m.prevLast?'down':'flat';
  lastEl.className='last '+dir;
  lastEl.innerHTML=`<span class="arrow">${dir==='up'?'▲':dir==='down'?'▼':'■'}</span>${fmtP(m.last)}g`;
  document.getElementById('spreadVal').textContent=(b!=null&&a!=null)?fmtP(a-b)+'g':'—';
  document.getElementById('midVal').textContent=fmtP(mid(m))+'g';
  document.getElementById('bookHint').textContent='live · '+(m.bids.length+m.asks.length)+' levels';

  // flash changed levels
  flashChanges('ask',asks); flashChanges('bid',bids);
}
function rowHtml(side,o,cumv,maxSize,best){
  if(!o) return `<div class="row ${side} empty"><span class="price">0</span><span class="size">0</span><span class="cum">0</span><span class="bar"></span></div>`;
  const w=Math.max(4,(o.size/maxSize)*100);
  const mine=o.owner==='you'?'mine':'';
  return `<div class="row ${side} ${best?'best':''} ${mine}" data-px="${o.price}">
    <span class="you">YOU</span>
    <span class="price">${fmtP(o.price)}</span>
    <span class="size">${o.size}</span>
    <span class="cum">${cumv}</span>
    <span class="bar" style="width:${w}%"></span>
  </div>`;
}
function flashChanges(side,arr){
  const map={}; arr.forEach(o=>map[o.price.toFixed(1)]=o.size);
  const cont=document.getElementById(side==='ask'?'askRows':'bidRows');
  cont.querySelectorAll('.row').forEach(r=>{
    const px=r.dataset.px; if(!px)return;
    const old=prevSizes[side][px], now=map[px];
    if(now!=null && old!=null && now!==old){
      r.classList.remove('fup','fdn'); void r.offsetWidth;
      r.classList.add(now>old?'fup':'fdn');
    }
  });
  prevSizes[side]=map;
}

let depthCtx;
function renderDepth(){
  const m=markets[active];
  const cv=document.getElementById('depth');
  const w=cv.clientWidth||cv.parentElement.clientWidth-24, h=190, dpr=window.devicePixelRatio||1;
  if(cv.width!==w*dpr){ cv.width=w*dpr; cv.height=h*dpr; }
  if(!depthCtx) depthCtx=cv.getContext('2d');
  const ctx=depthCtx; ctx.setTransform(dpr,0,0,dpr,0,0); ctx.clearRect(0,0,w,h);

  const bids=m.bids.slice(0,VIEW_LEVELS), asks=m.asks.slice(0,VIEW_LEVELS);
  if(!bids.length||!asks.length) return;
  // cumulative
  let c=0; const bPts=bids.map(o=>{c+=o.size;return{p:o.price,c}});
  c=0; const aPts=asks.map(o=>{c+=o.size;return{p:o.price,c}});
  const pMin=Math.min(bPts[bPts.length-1].p, m.fair-1), pMax=Math.max(aPts[aPts.length-1].p, m.fair+1);
  const cMax=Math.max(bPts[bPts.length-1].c, aPts[aPts.length-1].c)*1.08;
  const midP=mid(m);
  const X=p=>((p-pMin)/(pMax-pMin))*w;
  const Y=v=>h-8-(v/cMax)*(h-22);

  // grid
  ctx.strokeStyle='rgba(255,255,255,.05)'; ctx.lineWidth=1;
  for(let i=0;i<=3;i++){ const yy=8+i*(h-22)/3; ctx.beginPath();ctx.moveTo(0,yy);ctx.lineTo(w,yy);ctx.stroke(); }

  // bids area (green) — from mid leftwards (best bid near mid)
  const css=getComputedStyle(document.documentElement);
  const bid=css.getPropertyValue('--bid').trim(), ask=css.getPropertyValue('--ask').trim();
  drawStep(ctx, bPts.slice().reverse(), X, Y, h, bid, true, midP);
  drawStep(ctx, aPts, X, Y, h, ask, false, midP);

  // mid line
  ctx.strokeStyle='rgba(216,180,90,.5)';ctx.setLineDash([3,3]);ctx.beginPath();
  ctx.moveTo(X(midP),6);ctx.lineTo(X(midP),h-6);ctx.stroke();ctx.setLineDash([]);
  ctx.fillStyle='rgba(216,180,90,.85)';ctx.font='600 10px '+css.getPropertyValue('--mono');
  ctx.textAlign='center';ctx.fillText(fmtP(midP),X(midP),h-1);
}
function drawStep(ctx,pts,X,Y,h,color,leftToMid,midP){
  if(!pts.length)return;
  ctx.beginPath();
  const x0=X(leftToMid?pts[0].p:midP);
  ctx.moveTo(leftToMid?X(pts[0].p):X(midP), Y(0));
  if(leftToMid){
    // pts sorted ascending price toward mid
    ctx.lineTo(X(pts[0].p),Y(pts[0].c));
    for(let i=1;i<pts.length;i++){ ctx.lineTo(X(pts[i].p),Y(pts[i-1].c)); ctx.lineTo(X(pts[i].p),Y(pts[i].c)); }
    ctx.lineTo(X(midP),Y(pts[pts.length-1].c));
    ctx.lineTo(X(midP),Y(0));
  } else {
    ctx.lineTo(X(midP),Y(pts[0].c));
    for(let i=1;i<pts.length;i++){ ctx.lineTo(X(pts[i].p),Y(pts[i-1].c)); ctx.lineTo(X(pts[i].p),Y(pts[i].c)); }
    ctx.lineTo(X(pts[pts.length-1].p),Y(pts[pts.length-1].c));
    ctx.lineTo(X(pts[pts.length-1].p),Y(0));
  }
  ctx.closePath();
  ctx.globalAlpha=.20; ctx.fillStyle=color; ctx.fill();
  ctx.globalAlpha=1; ctx.lineWidth=1.6; ctx.strokeStyle=color; ctx.stroke();
}

function renderTape(){
  const m=markets[active];
  document.getElementById('tape').innerHTML=m.trades.map(t=>{
    const up=t.side==='buy';
    const cls=up?'up':'down';
    const fresh=t.fresh?'new':''; t.fresh=false;
    const ago=Math.max(0,Math.round((Date.now()-t.t)/1000));
    return `<div class="trow ${fresh}"><span class="tp ${cls}">${up?'▲':'▼'} ${fmtP(t.price)}</span><span class="ts">×${t.size}</span><span class="tt">${ago}s</span></div>`;
  }).join('');
}

function renderHoldings(){
  const sw=player.inv.sword, sh=player.inv.shield;
  document.getElementById('hSword').innerHTML=`${sw.qty} <small>${sw.reserved?('· '+sw.reserved+' resting'):'available'}</small>`;
  document.getElementById('hShield').innerHTML=`${sh.qty} <small>${sh.reserved?('· '+sh.reserved+' resting'):'available'}</small>`;
}

function renderOrders(){
  const m=markets[active];
  const mine=[...m.asks.filter(o=>o.owner==='you'), ...m.bids.filter(o=>o.owner==='you')]
    .sort((a,b)=>b.price-a.price);
  document.getElementById('ordCount').textContent=mine.length?`(${mine.length})`:'';
  const list=document.getElementById('ordList');
  if(!mine.length){ list.innerHTML=`<div class="ordempty">No resting orders. Place a limit order to sit in the book.</div>`; return; }
  list.innerHTML=mine.map(o=>{
    const buy=o.side==='bid';
    return `<div class="ord">
      <span class="tag ${buy?'b':'s'}">${buy?'BUY':'SELL'}</span>
      <span class="od">${o.size} ${ITEMS[m.key].icon} @</span>
      <span class="op">${fmtP(o.price)}g</span>
      <button class="cancel" data-id="${o.id}">Cancel</button>
    </div>`;
  }).join('');
  list.querySelectorAll('.cancel').forEach(b=>b.onclick=()=>cancelOrder(m,b.dataset.id));
}

/* ---------- ticket UI ---------- */
function syncTicket(){
  const m=markets[active];
  document.getElementById('ticketHint').textContent=`${ITEMS[m.key].icon} ${ITEMS[m.key].name}`;
  const isLimit=ticket.type==='limit';
  document.getElementById('priceField').style.display=isLimit?'block':'none';
  // place button
  const pb=document.getElementById('place');
  pb.className='place '+(ticket.side==='buy'?'buy':'sell');
  pb.textContent=`${ticket.side==='buy'?'Buy':'Sell'} ${ITEMS[m.key].icon} ${ITEMS[m.key].name.split(' ')[1]}`;
  // estimate
  const qty=Math.max(1,Math.round(Number(document.getElementById('qty').value)||1));
  const est=document.getElementById('est'), lbl=document.getElementById('estLbl'),
        val=document.getElementById('estVal'), note=document.getElementById('estNote');
  if(isLimit){
    const price=roundTick(Number(document.getElementById('price').value)||0,m.tick);
    const ba=bestAsk(m), bb=bestBid(m), md=mid(m);
    if(ticket.side==='buy'){
      lbl.textContent='If filled, you pay';
      val.textContent=price>0?fmtG(qty*price)+'g':'—';
      if(price<=0) note.textContent='Set a price above.';
      else if(ba!=null && price>=ba)
        note.innerHTML=`Buys now — your price meets sellers at ${fmtP(ba)}g.<br>Acts like a market order, up to your price.`;
      else
        note.innerHTML=`Waits in the book at ${fmtP(price)}g.<br>${fmtP(Math.max(0,md-price))}g under mid · buys only if a seller drops to you.`;
    } else {
      lbl.textContent='If filled, you get';
      val.textContent=price>0?fmtG(qty*price)+'g':'—';
      if(price<=0) note.textContent='Set a price above.';
      else if(bb!=null && price<=bb)
        note.innerHTML=`Sells now — buyers are already at ${fmtP(bb)}g.<br>Acts like a market order, down to your price.`;
      else
        note.innerHTML=`Waits in the book at ${fmtP(price)}g.<br>${fmtP(Math.max(0,price-md))}g over mid · sells only if a buyer rises to you.`;
    }
  } else {
    if(ticket.side==='buy'){
      lbl.textContent='Est. cost'; const r=peek(m,'buy',qty);
      val.textContent=r.filled?`~${fmtG(r.spend)}g`:'—';
      note.textContent=r.filled?`avg ${fmtP(r.spend/r.filled)}g · fills now`:'no sellers';
    } else {
      lbl.textContent='Est. receive'; const r=peek(m,'sell',qty);
      val.textContent=r.filled?`~${fmtG(r.spend)}g`:'—';
      note.textContent=r.filled?`avg ${fmtP(r.spend/r.filled)}g · fills now`:'no buyers';
    }
  }
}
// non-destructive estimate of a market fill
function peek(m, side, qty){
  const book=side==='buy'?m.asks:m.bids; let rem=qty,filled=0,spend=0;
  for(const lvl of book){ if(lvl.owner==='you')continue; const t=Math.min(lvl.size,rem); filled+=t;spend+=t*lvl.price;rem-=t; if(rem<=0)break; }
  return {filled,spend};
}
function resetTicketDefaults(){
  const m=markets[active];
  const pf=document.getElementById('price');
  pf.value = ticket.side==='buy' ? (bestAsk(m)!=null?fmtP(bestAsk(m)):fmtP(m.fair)) : (bestBid(m)!=null?fmtP(bestBid(m)):fmtP(m.fair));
  syncTicket();
}

let msgTimer;
function flash(text,type){ const el=document.getElementById('msg'); el.textContent=text; el.className='msg '+(type||'info');
  clearTimeout(msgTimer); msgTimer=setTimeout(()=>{ el.textContent=''; el.className='msg'; },4200); }
function clearMsg(){ const el=document.getElementById('msg'); el.textContent=''; el.className='msg'; }

/* ---------- wire up controls ---------- */
function bind(){
  document.getElementById('guideBtn').onclick=()=>document.getElementById('guide').classList.toggle('open');
  document.getElementById('resetBtn').onclick=resetGame;

  const segBS=document.getElementById('segBS');
  segBS.querySelectorAll('button').forEach(b=>b.onclick=()=>{
    ticket.side=b.dataset.on; segBS.querySelectorAll('button').forEach(x=>x.classList.toggle('on',x===b));
    resetTicketDefaults();
  });
  const segTY=document.getElementById('segTY');
  segTY.querySelectorAll('button').forEach(b=>b.onclick=()=>{
    ticket.type=b.dataset.on; segTY.querySelectorAll('button').forEach(x=>x.classList.toggle('on',x===b));
    resetTicketDefaults();
  });

  const qty=document.getElementById('qty');
  document.getElementById('qUp').onclick=()=>{ qty.value=Math.max(1,(+qty.value||0)+1); syncTicket(); };
  document.getElementById('qDn').onclick=()=>{ qty.value=Math.max(1,(+qty.value||1)-1); syncTicket(); };
  qty.oninput=syncTicket;

  const price=document.getElementById('price');
  const tickStep=()=>markets[active].tick;
  document.getElementById('pUp').onclick=()=>{ price.value=fmtP(roundTick((+price.value||0)+tickStep(),tickStep())); syncTicket(); };
  document.getElementById('pDn').onclick=()=>{ price.value=fmtP(Math.max(tickStep(),roundTick((+price.value||tickStep())-tickStep(),tickStep()))); syncTicket(); };
  price.oninput=syncTicket;

  document.getElementById('place').onclick=placeOrder;

  document.getElementById('learnBtn').onclick=()=>LESSON.open();
  document.getElementById('lessonClose').onclick=()=>LESSON.close();
  document.getElementById('lessonBack').onclick=e=>{ if(e.target.id==='lessonBack') LESSON.close(); };
  document.querySelectorAll('.ltab').forEach(t=>t.onclick=()=>LESSON.setTab(t.dataset.tab));
  window.addEventListener('keydown',e=>{ if(e.key==='Escape') LESSON.close(); });

  window.addEventListener('resize',()=>renderDepth());
}

function resetGame(){
  player.gold=START_GOLD; player.reservedGold=0;
  player.inv={ sword:{qty:START_INV.sword,reserved:0}, shield:{qty:START_INV.shield,reserved:0} };
  for(const k in ITEMS){ markets[k]=newMarket(k); }
  player.startNet=netWorth();
  resetTicketDefaults(); renderAll(); flash('Sandbox reset — back to 10,000g.','info');
}

/* ============================================================
   LEARN-TO-TRADE — interactive lessons (uses its own fixed
   practice book so examples are deterministic and teachable)
   ============================================================ */
const LESSON = (()=>{
  const ASKS=[{p:13.0,s:4},{p:13.5,s:6},{p:14.0,s:8}];  // best..worst
  const BIDS=[{p:12.5,s:5},{p:12.0,s:7},{p:11.5,s:6}];
  const DMID=(ASKS[0].p+BIDS[0].p)/2;                   // 12.75
  const maxS=()=>Math.max(...ASKS.map(a=>a.s),...BIDS.map(b=>b.s));
  let tab='ml';

  function bookHtml(o={}){
    const ms=maxS(), hitA=o.hitA||{}, hitB=o.hitB||{};
    let h='';
    ASKS.slice().reverse().forEach(a=>{ const take=hitA[a.p], w=Math.max(8,a.s/ms*100);
      h+=`<div class="drow ask ${take?'hit':''}"><span class="dp">${a.p.toFixed(1)}</span><span class="ds">${a.s}</span>${take?`<span class="take">you bought ${take}</span>`:''}<span class="dbar" style="width:${w}%"></span></div>`; });
    if(o.youAsk){ const w=Math.max(8,o.youAsk.s/ms*100);
      h+=`<div class="drow ask mine"><span class="dyou">YOU</span><span class="dp">${o.youAsk.p.toFixed(1)}</span><span class="ds">${o.youAsk.s}</span><span class="dbar" style="width:${w}%"></span></div>`; }
    h+=`<div class="dspread">spread <b>0.5g</b> · mid <b>${DMID.toFixed(2)}g</b></div>`;
    if(o.youBid){ const w=Math.max(8,o.youBid.s/ms*100);
      h+=`<div class="drow bid mine"><span class="dyou">YOU</span><span class="dp">${o.youBid.p.toFixed(1)}</span><span class="ds">${o.youBid.s}</span><span class="dbar" style="width:${w}%"></span></div>`; }
    BIDS.forEach(b=>{ const take=hitB[b.p], w=Math.max(8,b.s/ms*100);
      h+=`<div class="drow bid ${take?'hit':''}"><span class="dp">${b.p.toFixed(1)}</span><span class="ds">${b.s}</span>${take?`<span class="take">you sold ${take}</span>`:''}<span class="dbar" style="width:${w}%"></span></div>`; });
    return `<div class="dbook"><div class="dcap">Practice book — Basic Sword</div>${h}</div>`;
  }
  function fill(book,qty){ let rem=qty,legs=[],cost=0; for(const o of book){ const t=Math.min(o.s,rem); if(t<=0)break; legs.push({p:o.p,t}); cost+=t*o.p; rem-=t; if(rem<=0)break; } const f=qty-rem; return {legs,filled:f,cost,avg:f?cost/f:0}; }
  const legStr=l=>l.map(x=>`${x.t} @ ${x.p.toFixed(1)}`).join('  +  ');

  /* ---- Market vs Limit ---- */
  let mlState=null;
  function renderML(){
    document.getElementById('lessonBody').innerHTML=`
      <p class="lintro">Same goal — buy 3 swords — but two very different orders. Press each button and watch the practice book on the left.</p>
      <div class="dwrap">
        <div id="mlBook"></div>
        <div class="lside">
          <div class="lbtns">
            <button class="lbtn market" id="mlMkt">⚡ Market buy 3<small>Fills now at the best price available</small></button>
            <button class="lbtn limit" id="mlLim">⏳ Limit buy 3 @ 12.50<small>Rests in the book, waits for a seller</small></button>
          </div>
          <div class="result" id="mlRes"></div>
          <div><button class="lbtn reset" id="mlReset">↺ Reset book</button></div>
        </div></div>`;
    document.getElementById('mlMkt').onclick=()=>{mlState='m';drawML();};
    document.getElementById('mlLim').onclick=()=>{mlState='l';drawML();};
    document.getElementById('mlReset').onclick=()=>{mlState=null;drawML();};
    drawML();
  }
  function drawML(){
    const bk=document.getElementById('mlBook'), res=document.getElementById('mlRes');
    if(mlState==='m'){
      const r=fill(ASKS,3), hitA={}; r.legs.forEach(l=>hitA[l.p]=l.t);
      bk.innerHTML=bookHtml({hitA});
      res.innerHTML=`<p class="rt">⚡ Market buy — filled instantly</p>
        <p class="legs">${legStr(r.legs)}<br>avg paid <span class="big">${r.avg.toFixed(2)}g</span> · total ${r.cost.toFixed(1)}g</p>
        <p>You crossed the spread and took the cheapest seller. You own the swords <b>right now</b> — but you paid <span class="big">+${(r.avg-DMID).toFixed(2)}g</span> per unit over the mid. That gap is the price of speed.</p>
        <div class="takeaway"><b>Reach for a market order</b> when getting filled matters more than getting the perfect price.</div>`;
    } else if(mlState==='l'){
      bk.innerHTML=bookHtml({youBid:{p:12.5,s:3}});
      res.innerHTML=`<p class="rt">⏳ Limit buy — resting in the book</p>
        <p class="legs">3 @ 12.50 · waiting for a seller</p>
        <p>Your order now sits on the bid (tagged <b>YOU</b>). If a guild sells into it you buy at <span class="big">12.50g</span> — that's <span class="big">0.25g below</span> the mid, the opposite of paying the spread. The catch: it only fills if the market comes to your price, and it might not.</p>
        <div class="takeaway"><b>Reach for a limit order</b> when price matters more than speed and you're willing to wait.</div>`;
    } else {
      bk.innerHTML=bookHtml({});
      res.innerHTML=`<p>Pick an order above to see how it behaves. The <b>best ask is 13.0g</b> (cheapest place to buy) and the <b>best bid is 12.5g</b> (highest place to sell). The mid sits at <b>12.75g</b>.</p>`;
    }
  }

  /* ---- Good vs bad trades ---- */
  const SC=[
    { id:'g1', kind:'good', label:'Patient limit buy',
      view:()=>bookHtml({youBid:{p:12.5,s:3}}),
      title:'Joined the bid and got filled',
      legs:()=>'Bought 3 @ 12.50 — a seller hit your resting order',
      body:'You waited at the best bid instead of chasing. A seller came to you, so you bought below the mid and paid zero spread.',
      edge:()=>'+0.75g vs buying at mid  ·  0.25g cheaper per unit' },
    { id:'g2', kind:'good', label:'Sold into the ask',
      view:()=>bookHtml({youAsk:{p:13.0,s:3}}),
      title:'Posted at the ask and got lifted',
      legs:()=>'Sold 3 @ 13.00 — a buyer took your offer',
      body:'You let buyers come to you at the top of the book. You sold above the mid, collecting the spread instead of paying it.',
      edge:()=>'+0.75g vs selling at mid  ·  0.25g richer per unit' },
    { id:'b1', kind:'bad', label:'Chased size at market',
      view:()=>{ const r=fill(ASKS,10),h={}; r.legs.forEach(l=>h[l.p]=l.t); return bookHtml({hitA:h}); },
      title:'Walked the book buying 10 at market',
      legs:()=>{ const r=fill(ASKS,10); return legStr(r.legs)+`  →  avg ${r.avg.toFixed(2)}g`; },
      body:'Your order was bigger than the cheapest level, so it ate into pricier sellers — that\'s slippage. Each extra sword cost more than the last.',
      edge:()=>{ const r=fill(ASKS,10); return `−${((r.avg-DMID)*r.filled).toFixed(1)}g vs mid  ·  ${(r.avg-DMID).toFixed(2)}g worse per unit`; } },
    { id:'b2', kind:'bad', label:'Panic market sell',
      view:()=>{ const r=fill(BIDS,8),h={}; r.legs.forEach(l=>h[l.p]=l.t); return bookHtml({hitB:h}); },
      title:'Dumped 8 into the bids at market',
      legs:()=>{ const r=fill(BIDS,8); return legStr(r.legs)+`  →  avg ${r.avg.toFixed(2)}g`; },
      body:'Selling at market hits the highest bid first, then worse ones. You gave up the spread and slid down the book just to get out fast.',
      edge:()=>{ const r=fill(BIDS,8); return `−${((DMID-r.avg)*r.filled).toFixed(1)}g vs mid  ·  ${(DMID-r.avg).toFixed(2)}g worse per unit`; } },
  ];
  let sel='g1';
  function renderGB(){
    document.getElementById('lessonBody').innerHTML=`
      <p class="lintro">A “good” trade isn't about guessing direction — it's about <b>entry quality</b>: how much you pay or give up versus the fair mid price. Tap each example.</p>
      <div class="chips">${SC.map(s=>`<button class="chip ${s.kind} ${s.id===sel?'on':''}" data-id="${s.id}"><span class="pip"></span>${s.label}</button>`).join('')}</div>
      <div class="dwrap"><div id="gbBook"></div><div class="lside"><div class="result" id="gbRes"></div></div></div>`;
    document.querySelectorAll('.chip').forEach(c=>c.onclick=()=>{sel=c.dataset.id;renderGB();});
    drawGB();
  }
  function drawGB(){
    const s=SC.find(x=>x.id===sel);
    document.getElementById('gbBook').innerHTML=s.view();
    document.getElementById('gbRes').innerHTML=`
      <p class="rt"><span class="verdict ${s.kind}">${s.kind==='good'?'✓ good':'✗ bad'}</span>${s.title}</p>
      <p class="legs">${s.legs()}</p>
      <p>${s.body}</p>
      <div class="takeaway">Result: <b>${s.edge()}</b></div>`;
  }

  function render(){ document.querySelectorAll('.ltab').forEach(t=>t.classList.toggle('on',t.dataset.tab===tab)); tab==='ml'?renderML():renderGB(); }
  return {
    open(){ document.getElementById('lessonBack').classList.add('open'); render(); },
    close(){ document.getElementById('lessonBack').classList.remove('open'); },
    setTab(t){ tab=t; render(); }
  };
})();

/* ---------- boot ---------- */
function boot(){
  for(const k in ITEMS) markets[k]=newMarket(k);
  player.startNet=netWorth();
  bind();
  resetTicketDefaults();
  renderAll();
  setInterval(simTick, 1400);         // market churn + aggressors (slower, calmer pace)
  setInterval(()=>renderTape(), 1000); // refresh "Xs ago" timers
}
boot();
</script>
</body>
</html>
