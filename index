<!doctype html>
<html lang="zh-Hant">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>五大人格快速測驗</title>
  <style>
    :root { --gap: 14px; }
    body{
      font-family: system-ui, -apple-system, "Segoe UI", "PingFang TC", "Noto Sans TC", "Microsoft JhengHei", sans-serif;
      margin: 0;
      background: #f6f7fb;
      color: #111;
      line-height: 1.55;
    }
    .wrap{
      max-width: 980px;
      margin: 0 auto;
      padding: 22px 16px 60px;
    }
    .card{
      background: #fff;
      border-radius: 16px;
      box-shadow: 0 8px 24px rgba(0,0,0,.06);
      padding: 18px;
      margin-bottom: 16px;
    }
    h1{ font-size: 22px; margin: 0 0 6px; }
    .sub{ color:#444; margin:0; }
    .note{
      background:#fff7d6;
      border: 1px solid #ffe08a;
      border-radius: 12px;
      padding: 12px;
      color:#333;
      margin-top: 10px;
    }
    .grid{
      display: grid;
      grid-template-columns: 1fr;
      gap: var(--gap);
      margin-top: 10px;
    }
    @media (min-width: 860px){
      .grid{ grid-template-columns: 1fr 1fr; }
    }
    .q{
      border: 1px solid #e9e9ef;
      border-radius: 14px;
      padding: 12px;
      background: #fff;
    }
    .q-title{
      font-weight: 650;
      margin: 0 0 8px;
      font-size: 15px;
    }
    .row{
      display:flex;
      flex-wrap: wrap;
      gap: 10px;
      align-items: center;
    }
    .pill{
      display: inline-flex;
      align-items:center;
      gap: 8px;
      border: 1px solid #ddd;
      padding: 8px 10px;
      border-radius: 999px;
      cursor: pointer;
      user-select: none;
      background: #fff;
    }
    .pill input{ margin:0; }
    .legend{
      display:flex;
      gap: 10px;
      flex-wrap: wrap;
      color:#444;
      font-size: 13px;
      margin-top: 8px;
    }
    .btns{
      display:flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 12px;
    }
    button{
      border: 0;
      border-radius: 12px;
      padding: 10px 14px;
      cursor: pointer;
      font-weight: 650;
      font-size: 14px;
    }
    .primary{ background:#2b6cff; color:#fff; }
    .ghost{ background:#eef3ff; color:#163a9a; }
    .danger{ background:#ffecec; color:#8a1212; }
    .muted{ color:#666; font-size: 13px; margin-top: 6px;}
    .result{
      display:none;
      margin-top: 14px;
      border-top: 1px dashed #e6e6ef;
      padding-top: 14px;
    }
    .scorebar{
      margin-top: 10px;
      display:grid;
      gap: 10px;
    }
    .bar{
      background:#f0f2f7;
      border-radius: 999px;
      overflow: hidden;
      height: 12px;
      border: 1px solid #e3e6f0;
    }
    .fill{
      height: 100%;
      width: 0%;
      background: #2b6cff;
    }
    .barrow{
      display:grid;
      grid-template-columns: 140px 1fr 70px;
      gap: 10px;
      align-items:center;
    }
    .k{ font-weight: 650; }
    .tag{
      font-size: 12px;
      padding: 3px 10px;
      border-radius: 999px;
      background:#f2f2f2;
      display:inline-block;
      margin-left: 8px;
      color:#333;
    }
    .section-title{
      font-size: 16px;
      font-weight: 750;
      margin: 10px 0 6px;
    }
    ul{ margin: 6px 0 10px 18px; }
    .warn{
      color:#8a1212;
      background:#fff1f1;
      border:1px solid #ffd2d2;
      padding: 10px 12px;
      border-radius: 12px;
      display:none;
      margin-top: 12px;
    }
    .footer{
      color:#666;
      font-size: 12px;
      margin-top: 10px;
    }
    .small{
      font-size: 12px;
      color:#666;
    }
    .copy{
      margin-left:auto;
    }
    textarea{
      width: 100%;
      min-height: 120px;
      border-radius: 12px;
      border: 1px solid #e3e3ef;
      padding: 10px;
      font-family: inherit;
      font-size: 13px;
      background:#fbfbfe;
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card">
      <h1>五大人格快速測驗</h1>
      <p class="sub">請依照「你平常的樣子」作答。每題 1～5 分：1 非常不同意、5 非常同意。</p>
      <div class="note">
        這是簡化版測驗，用於自我理解與溝通參考，不等同臨床心理評估或診斷。
      </div>
    </div>

    <div class="card">
      <div class="legend">
        <span>1 非常不同意</span>
        <span>2 不同意</span>
        <span>3 普通</span>
        <span>4 同意</span>
        <span>5 非常同意</span>
      </div>

      <div id="questions" class="grid"></div>

      <div class="btns">
        <button class="primary" id="btnCalc">產生分析</button>
        <button class="ghost" id="btnAutoDemo" title="示範填入：你先前給的分數">套用示範分數</button>
        <button class="danger" id="btnReset">清空重填</button>
      </div>

      <div id="warn" class="warn"></div>

      <div id="result" class="result">
        <div style="display:flex; gap:10px; align-items:center; flex-wrap:wrap;">
          <div class="section-title" style="margin:0;">你的結果</div>
          <span class="small">（分數範圍：每個向度 2～10 分）</span>
          <button class="ghost copy" id="btnCopy">複製結果文字</button>
        </div>

        <div class="scorebar" id="bars"></div>

        <div class="section-title">綜合輪廓</div>
        <div id="profile"></div>

        <div class="section-title">向度解析</div>
        <div id="details"></div>

        <div class="section-title">建議</div>
        <div id="advice"></div>

        <div class="section-title">結果文字（方便貼到訊息）</div>
        <textarea id="plainText" readonly></textarea>

        <div class="footer">
          小提醒：分數只反映「自我回報」與當下狀態；情緒、壓力、近期事件都可能讓分數浮動。
        </div>
      </div>
    </div>
  </div>

<script>
(function(){
  // 題目（10 題）
  const items = [
    { id: 1, text: "我喜歡嘗試新事物、接觸不同觀點" },
    { id: 2, text: "我做事有計畫且重視細節" },
    { id: 3, text: "我在人多場合通常很自在" },
    { id: 4, text: "我容易因為別人的情緒受影響" },
    { id: 5, text: "我願意體諒別人的感受" },
    { id: 6, text: "我常有創意或想法很多" },
    { id: 7, text: "我討厭事情雜亂無章" },
    { id: 8, text: "我喜歡主動發言" },
    { id: 9, text: "我容易焦慮或想很多" },
    { id: 10, text: "我會為了維持關係而退一步" }
  ];

  // 五大向度（每個向度 2 題）
  const dims = [
    {
      key: "open",
      name: "開放性",
      desc: "創意、好奇、思維彈性與探索傾向",
      q: [1,6]
    },
    {
      key: "con",
      name: "嚴謹性",
      desc: "自律、計畫性、可靠度與執行力",
      q: [2,7]
    },
    {
      key: "ext",
      name: "外向性",
      desc: "社交能量、主動表達與外顯行動傾向",
      q: [3,8]
    },
    {
      key: "neu",
      name: "情緒敏感度",
      desc: "情緒波動與壓力反應傾向（分數高表示較敏感）",
      q: [4,9]
    },
    {
      key: "agr",
      name: "宜人性",
      desc: "同理、合作、關係維持與體諒傾向",
      q: [5,10]
    }
  ];

  // 建立題目介面
  const qWrap = document.getElementById("questions");
  items.forEach(it=>{
    const div = document.createElement("div");
    div.className = "q";
    div.innerHTML = `
      <p class="q-title">第 ${it.id} 題：${it.text}</p>
      <div class="row" role="group" aria-label="第${it.id}題分數">
        ${[1,2,3,4,5].map(v => `
          <label class="pill">
            <input type="radio" name="q${it.id}" value="${v}">
            <span>${v}</span>
          </label>
        `).join("")}
      </div>
    `;
    qWrap.appendChild(div);
  });

  function getAnswer(n){
    const el = document.querySelector(`input[name="q${n}"]:checked`);
    return el ? Number(el.value) : null;
  }

  function setAnswer(n, v){
    const el = document.querySelector(`input[name="q${n}"][value="${v}"]`);
    if(el) el.checked = true;
  }

  function clearAll(){
    items.forEach(it=>{
      const checked = document.querySelector(`input[name="q${it.id}"]:checked`);
      if(checked) checked.checked = false;
    });
    hideWarn();
    hideResult();
    window.scrollTo({ top: 0, behavior: "smooth" });
  }

  function showWarn(msg){
    const w = document.getElementById("warn");
    w.textContent = msg;
    w.style.display = "block";
  }
  function hideWarn(){
    const w = document.getElementById("warn");
    w.textContent = "";
    w.style.display = "none";
  }
  function showResult(){ document.getElementById("result").style.display = "block"; }
  function hideResult(){ document.getElementById("result").style.display = "none"; }

  // 分數區間：每向度 2~10
  function levelLabel(sum){
    if(sum <= 4) return { label: "偏低", tag: "偏低" };
    if(sum <= 7) return { label: "中等", tag: "中等" };
    return { label: "偏高", tag: "偏高" };
  }

  function inferProfile(scores){
    // 依你的原本那種「客觀第三者」文字風格，組出輪廓描述
    const open = scores.open.sum, con = scores.con.sum, ext = scores.ext.sum, neu = scores.neu.sum, agr = scores.agr.sum;

    const parts = [];

    // 開放性
    if(open >= 8) parts.push("思維彈性與探索傾向明顯");
    else if(open <= 4) parts.push("偏好熟悉路徑與務實做法");
    else parts.push("在新舊之間能取得平衡");

    // 嚴謹性
    if(con >= 8) parts.push("做事有結構、可依賴度高");
    else if(con <= 4) parts.push("較隨性，重視當下效率與彈性");
    else parts.push("有一定規劃力，也保留彈性");

    // 外向性（可出現矛盾型：一題低一題高）
    const q3 = scores.ext.qValues[0], q8 = scores.ext.qValues[1];
    if(q3 <= 2 && q8 >= 4){
      parts.push("偏「任務型表達」：不一定享受人多場合，但需要時能站出來");
    }else{
      if(ext >= 8) parts.push("外顯行動與表達能量偏強");
      else if(ext <= 4) parts.push("偏內向，重視獨處與精準互動");
      else parts.push("社交能量中等，視情境調整");
    }

    // 情緒敏感度
    if(neu >= 8) parts.push("情緒敏感度高，對壓力與氛圍反應較快");
    else if(neu <= 4) parts.push("情緒穩定度高，遇事較能保持平衡");
    else parts.push("情緒反應中等，近期狀態會影響感受");

    // 宜人性
    if(agr >= 8) parts.push("重視關係品質與互相體諒");
    else if(agr <= 4) parts.push("較直接、以原則與效率為先");
    else parts.push("能同理他人，也能保留自我界線");

    return "・" + parts.join("\n・");
  }

  function dimWriteup(dimKey, sum){
    // 每向度給：判讀 / 優勢 / 可能盲點（以客觀語氣）
    const lv = levelLabel(sum).label;

    const map = {
      open: {
        high: {
          judge: "對新資訊、新方法接受度高，容易從不同角度看事情。",
          pros: ["學習快、能整合多元觀點", "適合企劃、設計、策略與問題拆解", "遇到變動時較能找到替代方案"],
          cons: ["想法多時，決策可能拉長", "理想與現實落差時，容易感到挫折或焦躁"]
        },
        mid: {
          judge: "既能接受新做法，也會評估成本與風險後再投入。",
          pros: ["想得到也做得到", "兼顧創意與務實", "能在團隊中當折衷整合者"],
          cons: ["遇到高度不確定時，可能需要更多資訊才安心"]
        },
        low: {
          judge: "偏好可預期、可複製的方式，重視實用與穩定。",
          pros: ["落地能力強", "執行效率高", "對流程與風險較敏銳"],
          cons: ["面對快速變動或需要創新時，可能覺得不必要或耗能"]
        }
      },
      con: {
        high: {
          judge: "規劃與自律傾向明顯，傾向把事情做完整、做到位。",
          pros: ["可靠、守時、交付品質高", "能把複雜任務拆解成步驟", "適合需要長期耕耘的目標"],
          cons: ["容易對自己或他人標準較高", "完美傾向可能讓節奏變慢"]
        },
        mid: {
          judge: "有基本架構感，也願意因情境調整做法。",
          pros: ["能兼顧效率與品質", "遇到變動也不至於失序", "適合多工環境"],
          cons: ["在壓力大時，規劃可能被臨時事件打亂"]
        },
        low: {
          judge: "更重視彈性與臨場反應，不喜歡被流程綁住。",
          pros: ["反應快、臨場解決能力強", "適合快速迭代與探索型工作"],
          cons: ["若缺少外部結構，容易拖延或遺漏細節"]
        }
      },
      ext: {
        high: {
          judge: "表達與外顯行動能量高，偏向用互動推進事情。",
          pros: ["敢表達、帶動場域", "適合需要說服、協調、主持的角色", "行動啟動快"],
          cons: ["在需要長時間獨立深度工作時，可能較不耐"]
        },
        mid: {
          judge: "社交能量視情境而定，能在內外向之間切換。",
          pros: ["該出手時能出手", "也能保持獨立思考", "適合需要協作又要專注的工作型態"],
          cons: ["若環境要求長期高度社交，可能覺得消耗"]
        },
        low: {
          judge: "偏好精準互動與保留個人空間，不以熱絡社交為主。",
          pros: ["專注力與深度思考強", "較不受場面影響，能冷靜評估", "適合需要洞察與分析的任務"],
          cons: ["在需要大量曝光或即興社交時，可能覺得吃力"]
        }
      },
      neu: {
        high: {
          judge: "情緒與壓力反應較敏銳，容易注意到關係與氛圍的變化。",
          pros: ["感受力強、能察覺細節", "對風險與問題早期訊號敏感", "同理更貼近真實狀態"],
          cons: ["容易內耗、反覆思考", "外界評價或不確定性會放大壓力", "需要更明確的界線與節奏來承接"]
        },
        mid: {
          judge: "情緒反應中等，會受狀態影響，但通常能自行回穩。",
          pros: ["能感受他人，也保有理性評估", "壓力下仍能維持基本運作"],
          cons: ["當壓力長期累積時，仍可能突然爆量"]
        },
        low: {
          judge: "情緒穩定度較高，遇事通常能保持平衡。",
          pros: ["抗壓穩、較不受外界影響", "決策不易被情緒帶走"],
          cons: ["可能較不容易察覺自己其實累了，或忽略他人情緒訊號"]
        }
      },
      agr: {
        high: {
          judge: "重視合作與關係品質，傾向先理解再回應。",
          pros: ["同理強、溝通溫和", "容易建立信任", "適合需要陪伴與協作的情境"],
          cons: ["遇到衝突時可能傾向先退讓", "需要練習把界線說清楚，避免累積委屈"]
        },
        mid: {
          judge: "能同理也能堅持原則，傾向看情境做取捨。",
          pros: ["合作時好相處、但不失立場", "能在關係與效率之間平衡"],
          cons: ["在價值衝突大的情境，可能會猶豫要偏向哪一邊"]
        },
        low: {
          judge: "較直接、以原則與目標為先，不會為了和諧而犧牲效率。",
          pros: ["決策果斷", "談判與推進力強", "界線清晰"],
          cons: ["他人可能覺得你較冷或不夠柔和，需要刻意補上說明與同理"]
        }
      }
    };

    function pickBand(sum){
      if(sum <= 4) return "low";
      if(sum <= 7) return "mid";
      return "high";
    }

    const band = pickBand(sum);
    return map[dimKey][band];
  }

  function buildAdvice(scores){
    const open = scores.open.sum, con = scores.con.sum, ext = scores.ext.sum, neu = scores.neu.sum, agr = scores.agr.sum;

    const lines = [];

    // 以「可操作」為主，不講抽象口號
    if(neu >= 8 && con >= 6){
      lines.push("用「結構」承接情緒：把困擾拆成可處理的三件事（現在能做／需要資訊／先放下），每次只處理一件。");
    }else if(neu >= 8){
      lines.push("壓力上來時先降低不確定：把你正在擔心的事情具體化（寫下來、列條件），避免在腦內反覆打轉。");
    }

    if(open >= 8 && con >= 8){
      lines.push("你有創意也能落地，適合把「新想法」做成小實驗：先跑一輪最小版本，再決定要不要擴大。");
    }else if(open >= 8){
      lines.push("想法多時，先定「一句話目標」與「停止條件」（做到什麼程度就先交付），避免越想越散。");
    }

    // 外向/內向使用建議
    const q3 = scores.ext.qValues[0], q8 = scores.ext.qValues[1];
    if(q3 <= 2 && q8 >= 4){
      lines.push("你偏任務型表達：把需要曝光的事情設計成有腳本、有流程（開場、重點、收尾），會明顯降低消耗。");
    }else if(ext <= 4){
      lines.push("把重要互動改成「少量但高品質」：提前準備問題清單，縮短寒暄、拉高有效交流。");
    }else if(ext >= 8){
      lines.push("你推進力強，但要留意過度社交造成疲憊：固定保留一段不被打擾的深度時間。");
    }

    if(agr >= 8){
      lines.push("關係上容易先體諒別人：遇到界線議題時，先說事實＋需求＋可行方案，避免只用退讓換和諧。");
    }

    return "・" + lines.join("\n・");
  }

  function compute(){
    hideWarn();

    const answers = {};
    const missing = [];
    items.forEach(it=>{
      const v = getAnswer(it.id);
      if(v === null) missing.push(it.id);
      else answers[it.id] = v;
    });

    if(missing.length){
      showWarn("你還有題目沒填：第 " + missing.join("、") + " 題。請先完成作答。");
      hideResult();
      return;
    }

    // 計算每向度分數
    const scores = {};
    dims.forEach(d=>{
      const qv = d.q.map(n => answers[n]);
      const sum = qv.reduce((a,b)=>a+b,0);
      scores[d.key] = {
        name: d.name,
        desc: d.desc,
        sum,
        qValues: qv
      };
    });

    // 畫分數條
    const bars = document.getElementById("bars");
    bars.innerHTML = "";
    dims.forEach(d=>{
      const sc = scores[d.key].sum; // 2~10
      const pct = Math.round(((sc - 2) / 8) * 100); // 0~100
      const lvl = levelLabel(sc).label;

      const row = document.createElement("div");
      row.className = "barrow";
      row.innerHTML = `
        <div>
          <span class="k">${d.name}</span>
          <span class="tag">${lvl}</span>
        </div>
        <div class="bar" aria-label="${d.name}分數條">
          <div class="fill" style="width:${pct}%"></div>
        </div>
        <div style="text-align:right; font-weight:650;">${sc} / 10</div>
      `;
      bars.appendChild(row);
    });

    // 綜合輪廓
    const profile = document.getElementById("profile");
    profile.innerHTML = `<pre style="white-space:pre-wrap; margin:6px 0 0; font-family: inherit;">${inferProfile(scores)}</pre>`;

    // 向度解析
    const details = document.getElementById("details");
    details.innerHTML = "";
    dims.forEach(d=>{
      const sc = scores[d.key].sum;
      const lv = levelLabel(sc).label;
      const w = dimWriteup(d.key, sc);

      const box = document.createElement("div");
      box.className = "q";
      box.innerHTML = `
        <div style="display:flex; align-items:baseline; gap:10px; flex-wrap:wrap;">
          <div style="font-weight:800; font-size:15px;">${d.name}<span class="tag">${lv}</span></div>
          <div class="small">${d.desc}</div>
        </div>
        <div style="margin-top:10px;">
          <div class="k">判讀</div>
          <div>${w.judge}</div>
          <div style="margin-top:8px;" class="k">優勢</div>
          <ul>${w.pros.map(x=>`<li>${x}</li>`).join("")}</ul>
          <div class="k">可能盲點</div>
          <ul>${w.cons.map(x=>`<li>${x}</li>`).join("")}</ul>
        </div>
      `;
      details.appendChild(box);
    });

    // 建議
    document.getElementById("advice").innerHTML =
      `<pre style="white-space:pre-wrap; margin:6px 0 0; font-family: inherit;">${buildAdvice(scores)}</pre>`;

    // 文字版輸出
    const lines = [];
    lines.push("五大人格快速測驗結果");
    lines.push("");
    dims.forEach(d=>{
      const sc = scores[d.key].sum;
      const lv = levelLabel(sc).label;
      lines.push(`${d.name}：${sc}/10（${lv}）`);
    });
    lines.push("");
    lines.push("綜合輪廓");
    lines.push(inferProfile(scores).replaceAll("・","- "));
    lines.push("");
    lines.push("建議");
    lines.push(buildAdvice(scores).replaceAll("・","- "));
    document.getElementById("plainText").value = lines.join("\n");

    showResult();
    document.getElementById("result").scrollIntoView({ behavior: "smooth", block: "start" });
  }

  // 按鈕事件
  document.getElementById("btnCalc").addEventListener("click", compute);
  document.getElementById("btnReset").addEventListener("click", clearAll);

  // 你剛剛提供的示範分數：5 4 1 5 5 4 4 5 5 4
  document.getElementById("btnAutoDemo").addEventListener("click", ()=>{
    const demo = [5,4,1,5,5,4,4,5,5,4];
    demo.forEach((v, idx)=> setAnswer(idx+1, v));
    hideWarn();
  });

  document.getElementById("btnCopy").addEventListener("click", async ()=>{
    const txt = document.getElementById("plainText").value || "";
    try{
      await navigator.clipboard.writeText(txt);
      alert("已複製結果文字");
    }catch(e){
      alert("複製失敗：你的瀏覽器可能不允許剪貼簿操作。你可以直接手動全選下方文字複製。");
    }
  });
})();
</script>
</body>
</html>
