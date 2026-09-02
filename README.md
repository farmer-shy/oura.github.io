# oura.github.io

<!-- saved from url=(0065)file:///Users/macos/Downloads/oura_commander_dashboard%20(1).html -->
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"></head><body><h2 class="sr-only">Oura Ring Commander Dashboard — unit physiological readiness for the selected reporting period, sourced from participant biometric data and operational tempo records.</h2>

<style>
.ocd-hdr{background:#0D1B2A;border-radius:12px 12px 0 0;padding:14px 20px;display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
.ocd-hdr-eyebrow{color:#7B9EBC;font-size:10px;letter-spacing:.1em;text-transform:uppercase;margin-bottom:3px}
.ocd-hdr-title{color:#fff;font-size:17px;font-weight:500;line-height:1.2}
.ocd-hdr-meta{color:#7B9EBC;font-size:10px;letter-spacing:.08em;text-transform:uppercase;margin-bottom:3px}
.ocd-hdr-val{color:#fff;font-size:13px}
.ocd-sel{background:#1a2d44;color:#fff;border:0.5px solid #2E4A63;border-radius:4px;padding:4px 8px;font-size:13px;margin-top:2px}
.ocd-strip{padding:9px 20px;display:flex;align-items:center;justify-content:space-between;gap:8px;transition:background .2s}
.ocd-strip-left{display:flex;align-items:center;gap:8px}
.ocd-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0}
.ocd-strip-lbl{font-size:11px;font-weight:500;letter-spacing:.08em;text-transform:uppercase}
.ocd-strip-detail{font-size:11px}
.ocd-body{padding:14px 20px 0}
.ocd-kpi-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:10px;margin-bottom:12px}
.ocd-kpi{background:var(--surface-1);border:0.5px solid var(--border);border-radius:var(--radius);padding:12px 14px}
.ocd-kpi-lbl{font-size:10px;letter-spacing:.07em;text-transform:uppercase;color:var(--text-muted);margin-bottom:4px}
.ocd-kpi-num{font-size:26px;font-weight:500;line-height:1.05;font-variant-numeric:tabular-nums;color:var(--text-primary)}
.ocd-kpi-sub{font-size:11px;color:var(--text-secondary);margin:2px 0 8px}
.ocd-badge{display:inline-flex;align-items:center;gap:4px;font-size:10px;font-weight:500;padding:2px 8px;border-radius:4px}
.ocd-badge-dot{width:6px;height:6px;border-radius:50%}
.ocd-sec-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-bottom:12px}
.ocd-sec{background:var(--surface-1);border:0.5px solid var(--border);border-radius:var(--radius);padding:10px 12px}
.ocd-sec-lbl{font-size:10px;letter-spacing:.07em;text-transform:uppercase;color:var(--text-muted);margin-bottom:3px}
.ocd-sec-num{font-size:15px;font-weight:500;color:var(--text-primary);font-variant-numeric:tabular-nums}
.ocd-sec-delta{font-size:10px;color:var(--text-secondary);margin-top:1px}
.ocd-section{margin-bottom:12px}
.ocd-section-hdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px}
.ocd-section-ttl{font-size:11px;letter-spacing:.07em;text-transform:uppercase;color:var(--text-secondary);font-weight:500}
.ocd-legend{display:flex;gap:14px;flex-wrap:wrap}
.ocd-leg{display:flex;align-items:center;gap:5px;font-size:11px;color:var(--text-secondary)}
.ocd-leg-line{width:12px;height:2px;border-radius:2px}
.ocd-cmp table{width:100%;border-collapse:collapse;font-size:12px}
.ocd-cmp th{text-align:left;padding:4px 8px;font-size:10px;letter-spacing:.06em;text-transform:uppercase;color:var(--text-muted);font-weight:400;border-bottom:0.5px solid var(--border)}
.ocd-cmp td{padding:5px 8px;border-bottom:0.5px solid var(--border);color:var(--text-primary)}
.ocd-cmp .num{text-align:right;font-variant-numeric:tabular-nums}
.col-up{color:#1baf7a}.col-dn{color:#d03b3b}.col-nu{color:var(--text-secondary)}
.ocd-note{border-radius:var(--radius);border-left:3px solid;padding:12px 14px;margin-bottom:16px}
.ocd-note-hd{font-size:10px;letter-spacing:.08em;text-transform:uppercase;font-weight:500;margin-bottom:4px}
.ocd-note-body{font-size:12px;line-height:1.6;color:var(--text-primary)}
.ocd-footer{padding:0 20px 14px;font-size:10px;color:var(--text-muted);text-align:right}
</style>

<div class="ocd-hdr">
  <div>
    <div class="ocd-hdr-eyebrow">Oura Ring Trial — individual participant view</div>
    <div class="ocd-hdr-title">Commander Readiness Dashboard</div>
  </div>
  <div style="display:flex;gap:20px;align-items:flex-start;flex-wrap:wrap">
    <div>
      <div class="ocd-hdr-meta">Reporting period</div>
      <select id="periodSel" class="ocd-sel" onchange="updateDash()">
        <option value="11">May 2026</option>
        <option value="10">Apr 2026</option>
        <option value="9">Mar 2026</option>
        <option value="8">Feb 2026</option>
        <option value="7">Jan 2026</option>
        <option value="6">Dec 2025</option>
        <option value="5">Nov 2025</option>
        <option value="4">Oct 2025</option>
        <option value="3">Sep 2025</option>
        <option value="2">Aug 2025</option>
        <option value="1">Jul 2025</option>
        <option value="0">Jun 2025</option>
      </select>
    </div>
    <div>
      <div class="ocd-hdr-meta">Data current through</div>
      <div class="ocd-hdr-val">2 Jun 2026</div>
    </div>
  </div>
</div>

<div id="statusStrip" class="ocd-strip" style="background: rgb(255, 248, 225); border-bottom: 0.5px solid rgb(255, 224, 130);">
  <div class="ocd-strip-left">
    <div id="sDot" class="ocd-dot" style="background: rgb(249, 168, 37);"></div>
    <span id="sLbl" class="ocd-strip-lbl" style="color: rgb(230, 81, 0);">Unit status: caution</span>
  </div>
  <span id="sDetail" class="ocd-strip-detail" style="color: rgb(230, 81, 0);">Sleep declining · Readiness declining · Ops tempo elevated</span>
</div>

<div class="ocd-body">
  <div class="ocd-kpi-grid">
    <div class="ocd-kpi">
      <div class="ocd-kpi-lbl">Sleep score</div>
      <div class="ocd-kpi-num" id="kSleep">65.8</div>
      <div class="ocd-kpi-sub" id="kSleepSub">vs Apr '26: <span class="col-dn">2.9</span></div>
      <div id="kSleepBadge" class="ocd-badge"><span class="ocd-badge" style="background:#fff8e1;color:#e65100"><span class="ocd-badge-dot" style="background:#f9a825"></span>Caution</span></div>
    </div>
    <div class="ocd-kpi">
      <div class="ocd-kpi-lbl">Readiness score</div>
      <div class="ocd-kpi-num" id="kRead">73.7</div>
      <div class="ocd-kpi-sub" id="kReadSub">vs Apr '26: <span class="col-dn">2.8</span></div>
      <div id="kReadBadge" class="ocd-badge"><span class="ocd-badge" style="background:#fff8e1;color:#e65100"><span class="ocd-badge-dot" style="background:#f9a825"></span>Caution</span></div>
    </div>
    <div class="ocd-kpi">
      <div class="ocd-kpi-lbl">Activity score</div>
      <div class="ocd-kpi-num" id="kAct">93.8</div>
      <div class="ocd-kpi-sub" id="kActSub">vs Apr '26: <span class="col-up">+7.4</span></div>
      <div id="kActBadge" class="ocd-badge"><span class="ocd-badge" style="background:#e8f5e9;color:#2e7d32"><span class="ocd-badge-dot" style="background:#2e7d32"></span>Nominal</span></div>
    </div>
    <div class="ocd-kpi">
      <div class="ocd-kpi-lbl">Ops tempo</div>
      <div class="ocd-kpi-num" id="kTempo">3.1/5</div>
      <div class="ocd-kpi-sub" id="kTempoSub">High (3–3.5)</div>
      <div id="kTempoBadge" class="ocd-badge"><span class="ocd-badge" style="background:#ffebee;color:#b71c1c"><span class="ocd-badge-dot" style="background:#d32f2f"></span>At risk</span></div>
    </div>
  </div>

  <div class="ocd-sec-grid">
    <div class="ocd-sec">
      <div class="ocd-sec-lbl">Avg steps / day</div>
      <div class="ocd-sec-num" id="sSteps">8,073</div>
      <div class="ocd-sec-delta" id="sStepsDelta"><span class="col-up">+671</span></div>
    </div>
    <div class="ocd-sec">
      <div class="ocd-sec-lbl">Active calories</div>
      <div class="ocd-sec-num" id="sCals">559</div>
      <div class="ocd-sec-delta" id="sCalsDelta"><span class="col-up">+89 kcal</span></div>
    </div>
    <div class="ocd-sec">
      <div class="ocd-sec-lbl">Sedentary hrs</div>
      <div class="ocd-sec-num" id="sSed">7.0h</div>
      <div class="ocd-sec-delta" id="sSedDelta"><span class="col-dn">+0.1h</span></div>
    </div>
    <div class="ocd-sec">
      <div class="ocd-sec-lbl">Temp deviation</div>
      <div class="ocd-sec-num" id="sTemp">+0.04°C</div>
      <div class="ocd-sec-delta" id="sTempDelta"><span class="col-dn">+0.06°C</span></div>
    </div>
  </div>

  <div class="ocd-section">
    <div class="ocd-section-hdr">
      <div class="ocd-section-ttl">Wellness trend — 12 months</div>
      <div class="ocd-legend">
        <div class="ocd-leg"><div class="ocd-leg-line" style="background:#2a78d6"></div>Sleep</div>
        <div class="ocd-leg"><div class="ocd-leg-line" style="background:#1baf7a"></div>Readiness</div>
        <div class="ocd-leg"><div class="ocd-leg-line" style="background:#eb6834;height:0;border-top:2px dashed #eb6834;border-radius:0"></div>Activity</div>
      </div>
    </div>
    <div style="position:relative;height:180px">
      <canvas id="wellChart" role="img" aria-label="Line chart of sleep, readiness, and activity scores over 12 months, Jun 2025 to May 2026" width="2768" height="360" style="display: block; box-sizing: border-box; height: 180px; width: 1384px;">Sleep, readiness, and activity scores over 12 months.</canvas>
    </div>
  </div>

  <div class="ocd-section">
    <div class="ocd-section-hdr">
      <div class="ocd-section-ttl">Operational tempo (1 = routine · 5 = sustained high)</div>
    </div>
    <div style="position:relative;height:72px">
      <canvas id="tempoChart" role="img" aria-label="Bar chart of monthly operational tempo on a scale of 1 to 5, Jun 2025 to May 2026" width="2768" height="144" style="display: block; box-sizing: border-box; height: 72px; width: 1384px;">Operational tempo history over 12 months.</canvas>
    </div>
  </div>

  <div class="ocd-section ocd-cmp">
    <div class="ocd-section-hdr"><div class="ocd-section-ttl">Period comparison</div></div>
    <table>
      <thead>
        <tr>
          <th>Metric</th>
          <th class="num" id="thPeriod">May '26</th>
          <th class="num">vs prior month</th>
          <th class="num">vs 12-mo avg</th>
          <th>Direction</th>
        </tr>
      </thead>
      <tbody id="cmpBody"><tr><td>Sleep score</td><td class="num">65.8</td><td class="num"><span class="col-dn">2.9</span></td><td class="num"><span class="col-dn">-3.8</span></td><td style="font-size:10px"><span class="col-dn">▼ Lower</span></td></tr><tr><td>Readiness score</td><td class="num">73.7</td><td class="num"><span class="col-dn">2.8</span></td><td class="num"><span class="col-up">+0.4</span></td><td style="font-size:10px"><span class="col-dn">▼ Lower</span></td></tr><tr><td>Activity score</td><td class="num">93.8</td><td class="num"><span class="col-up">+7.4</span></td><td class="num"><span class="col-up">+8.5</span></td><td style="font-size:10px"><span class="col-up">▲ Higher</span></td></tr><tr><td>Avg steps / day</td><td class="num">8073</td><td class="num"><span class="col-up">+671</span></td><td class="num"><span class="col-up">+2912</span></td><td style="font-size:10px"><span class="col-up">▲ Higher</span></td></tr><tr><td>Active calories</td><td class="num">559</td><td class="num"><span class="col-up">+89</span></td><td class="num"><span class="col-up">+108</span></td><td style="font-size:10px"><span class="col-up">▲ Higher</span></td></tr><tr><td>Sedentary hrs</td><td class="num">7.0h</td><td class="num"><span class="col-dn">+0.1h</span></td><td class="num"><span class="col-dn">+1.2h</span></td><td style="font-size:10px"><span class="col-nu">◆ Stable</span></td></tr><tr><td>Ops tempo</td><td class="num">3.1/5</td><td class="num"><span class="col-dn">+2.0/5</span></td><td class="num"><span class="col-dn">+1.3/5</span></td><td style="font-size:10px"><span class="col-dn">▲ Higher</span></td></tr></tbody>
    </table>
  </div>

  <div id="cmdNote" class="ocd-note" style="background: rgb(255, 248, 225); border-left: 3px solid rgb(249, 168, 37); border-radius: var(--radius); padding: 12px 14px; margin-bottom: 16px;">
    <div id="cmdNoteHd" class="ocd-note-hd" style="color: rgb(230, 81, 0);">Commander attention recommended</div>
    <div id="cmdNoteBody" class="ocd-note-body"><strong>Risk:</strong> Sleep declined 2.9 pts vs prior month.<br><strong>Recommended action:</strong> investigate scheduling for circadian disruption factors</div>
  </div>
</div>

<div class="ocd-footer">Oura Ring Trial · 70 participants · Source: Oura Enterprise + Ops Tempo Log</div>

<script src="./oura_commander_dashboard_files/chart.umd.js"></script>
<script>
const MO = [
  {m:"Jun '25",sleep:68.7,readiness:73.5,activity:93.0,tempo:1.8,steps:5420,calories:421,sed:6.1,temp:0.08},
  {m:"Jul '25",sleep:72.2,readiness:74.1,activity:93.5,tempo:1.0,steps:6102,calories:452,sed:5.8,temp:-0.05},
  {m:"Aug '25",sleep:72.5,readiness:72.8,activity:89.0,tempo:2.1,steps:3200,calories:380,sed:4.2,temp:-0.12},
  {m:"Sep '25",sleep:67.3,readiness:67.5,activity:88.5,tempo:2.3,steps:2800,calories:351,sed:5.1,temp:0.03},
  {m:"Oct '25",sleep:79.2,readiness:78.0,activity:82.0,tempo:1.5,steps:2100,calories:281,sed:4.8,temp:-0.22},
  {m:"Nov '25",sleep:71.5,readiness:73.5,activity:85.0,tempo:1.8,steps:4800,calories:412,sed:5.4,temp:0.09},
  {m:"Dec '25",sleep:69.0,readiness:71.0,activity:80.0,tempo:2.2,steps:3900,calories:363,sed:5.9,temp:0.14},
  {m:"Jan '26",sleep:70.5,readiness:72.5,activity:84.0,tempo:1.5,steps:4200,calories:388,sed:5.6,temp:-0.08},
  {m:"Feb '26",sleep:71.0,readiness:73.0,activity:85.0,tempo:2.0,steps:4600,calories:401,sed:5.7,temp:0.01},
  {m:"Mar '26",sleep:70.0,readiness:71.5,activity:87.0,tempo:2.8,steps:5100,calories:435,sed:5.8,temp:0.06},
  {m:"Apr '26",sleep:68.7,readiness:76.5,activity:86.4,tempo:1.1,steps:7402,calories:470,sed:6.9,temp:-0.02},
  {m:"May '26",sleep:65.8,readiness:73.7,activity:93.8,tempo:3.1,steps:8073,calories:559,sed:7.0,temp:0.04}
];
const AVG12={sleep:69.6,readiness:73.3,activity:85.3,steps:5161,calories:451,sed:5.77,temp:0.018,tempo:1.84};

function getStatus(d){
  if(d.sleep<65||d.readiness<68)return'red';
  if(d.sleep<72||d.readiness<75||d.tempo>2.5)return'amber';
  return'green';
}
const SC={
  green:{bg:'#e8f5e9',border:'#a5d6a7',dot:'#2e7d32',text:'#1b5e20',label:'Unit status: ready'},
  amber:{bg:'#fff8e1',border:'#ffe082',dot:'#f9a825',text:'#e65100',label:'Unit status: caution'},
  red:  {bg:'#ffebee',border:'#ef9a9a',dot:'#d32f2f',text:'#b71c1c',label:'Unit status: at risk'}
};
const BADGE={
  green:{bg:'#e8f5e9',color:'#2e7d32',dot:'#2e7d32',lbl:'Nominal'},
  amber:{bg:'#fff8e1',color:'#e65100',dot:'#f9a825',lbl:'Caution'},
  red:  {bg:'#ffebee',color:'#b71c1c',dot:'#d32f2f',lbl:'At risk'}
};

function mkBadge(s){
  const b=BADGE[s];
  return`<span class="ocd-badge" style="background:${b.bg};color:${b.color}"><span class="ocd-badge-dot" style="background:${b.dot}"></span>${b.lbl}</span>`;
}
function mStatus(v,g,a){return v>=g?'green':v>=a?'amber':'red';}
function tStatus(t){return t<=2.0?'green':t<=2.8?'amber':'red';}
function tLabel(t){return t<=1.5?'Routine (1–1.5)':t<=2.5?'Elevated (2–2.5)':t<=3.5?'High (3–3.5)':'Sustained High (4–5)';}

function dStr(curr,prev,dec,unit,hg){
  if(prev==null)return'';
  const d=curr-prev,s=d>0?'+':'';
  const cl=(d>0&&hg)||(d<0&&!hg)?'col-up':d===0?'col-nu':'col-dn';
  return`<span class="${cl}">${s}${Math.abs(d).toFixed(dec)}${unit}</span>`;
}

function dirStr(d,hg){
  if(d==null)return'—';
  if(Math.abs(d)<0.15)return'<span class="col-nu">◆ Stable</span>';
  return d>0?(hg?'<span class="col-up">▲ Higher</span>':'<span class="col-dn">▲ Higher</span>'):(hg?'<span class="col-dn">▼ Lower</span>':'<span class="col-up">▼ Lower</span>');
}

function getNote(d,prev,s){
  const risks=[],recs=[];
  if(prev&&d.sleep<prev.sleep-1.5){risks.push(`Sleep declined ${(prev.sleep-d.sleep).toFixed(1)} pts vs prior month`);recs.push('investigate scheduling for circadian disruption factors');}
  if(d.sleep<68){risks.push(`Sleep score (${d.sleep.toFixed(1)}) below recommended operational floor`);recs.push('identify low-sleep individuals for targeted sleep hygiene intervention');}
  if(prev&&d.readiness<prev.readiness-2){risks.push(`Readiness dropped ${(prev.readiness-d.readiness).toFixed(1)} pts — cumulative fatigue likely`);recs.push('review duty cycle and schedule a recovery window within 2 weeks');}
  if(d.tempo>2.5){risks.push(`Ops tempo (${d.tempo.toFixed(1)}/5) is elevated — sustained load accelerates physiological cost`);recs.push('pre-schedule a low-intensity recovery week before the next high-tempo period');}
  if(d.sed>6.5){risks.push(`Sedentary hours (${d.sed.toFixed(1)} h/day) are high — physical output suppressed`);}
  if(risks.length===0){risks.push('All metrics within normal operational range');recs.push('maintain current scheduling and monitoring cadence');}
  const heads={green:'No immediate action required',amber:'Commander attention recommended',red:'Command action required'};
  return{head:heads[s],risk:risks[0],rec:recs[0]||'Continue monitoring current trajectory.'};
}

let wChart,tChart;

function buildCharts(){
  const isDark=window.matchMedia('(prefers-color-scheme: dark)').matches;
  const grid=isDark?'rgba(255,255,255,0.07)':'#e1e0d9';
  const tick=isDark?'#898781':'#898781';
  const labels=MO.map(m=>m.m);
  const base={responsive:true,maintainAspectRatio:false,animation:false,
    plugins:{legend:{display:false},tooltip:{mode:'index',intersect:false,callbacks:{
      label:ctx=>`${ctx.dataset.label}: ${ctx.parsed.y.toFixed(1)}`
    }}}};

  wChart=new Chart(document.getElementById('wellChart'),{type:'line',data:{labels,datasets:[
    {label:'Sleep',data:MO.map(m=>m.sleep),borderColor:'#2a78d6',borderWidth:2,pointBackgroundColor:'#2a78d6',pointRadius:3.5,pointHoverRadius:5,pointBorderColor:'#fff',pointBorderWidth:1.5,tension:.35,fill:false},
    {label:'Readiness',data:MO.map(m=>m.readiness),borderColor:'#1baf7a',borderWidth:2,pointBackgroundColor:'#1baf7a',pointRadius:3.5,pointHoverRadius:5,pointBorderColor:'#fff',pointBorderWidth:1.5,tension:.35,fill:false},
    {label:'Activity',data:MO.map(m=>m.activity),borderColor:'#eb6834',borderDash:[5,3],borderWidth:2,pointBackgroundColor:'#eb6834',pointRadius:3.5,pointHoverRadius:5,pointBorderColor:'#fff',pointBorderWidth:1.5,tension:.35,fill:false},
  ]},options:{...base,scales:{
    x:{grid:{color:grid},ticks:{color:tick,font:{size:9}},border:{display:false}},
    y:{min:55,max:100,grid:{color:grid},ticks:{color:tick,font:{size:9},stepSize:10},border:{display:false}}
  }}});

  tChart=new Chart(document.getElementById('tempoChart'),{type:'bar',data:{labels,datasets:[{
    label:'Ops Tempo',data:MO.map(m=>m.tempo),
    backgroundColor:MO.map(m=>m.tempo<=2.0?'rgba(27,175,122,.7)':m.tempo<=2.8?'rgba(249,168,37,.8)':'rgba(211,47,47,.75)'),
    borderRadius:3,barPercentage:.72
  }]},options:{...base,scales:{
    x:{display:false},
    y:{min:0,max:5,grid:{color:grid},ticks:{color:tick,font:{size:9},stepSize:1},border:{display:false}}
  }}});
}

function highlightMonth(i){
  if(!wChart)return;
  const pl=wChart.data.datasets[0].pointRadius.map?wChart.data.datasets[0].pointRadius:[3.5,3.5,3.5,3.5,3.5,3.5,3.5,3.5,3.5,3.5,3.5,3.5];
  [0,1,2].forEach(ds=>{
    wChart.data.datasets[ds].pointRadius=MO.map((_,j)=>j===i?7:3.5);
    wChart.data.datasets[ds].pointBorderWidth=MO.map((_,j)=>j===i?2:1.5);
  });
  wChart.update('none');
}

function updateDash(){
  const i=parseInt(document.getElementById('periodSel').value);
  const d=MO[i],prev=i>0?MO[i-1]:null;
  const s=getStatus(d),sc=SC[s];

  document.getElementById('statusStrip').style.cssText=`background:${sc.bg};border-bottom:0.5px solid ${sc.border}`;
  document.getElementById('sDot').style.background=sc.dot;
  const lbl=document.getElementById('sLbl');lbl.textContent=sc.label;lbl.style.color=sc.text;
  const det=document.getElementById('sDetail');
  const parts=[];
  if(prev&&d.sleep<prev.sleep-1.5)parts.push('Sleep declining');
  if(prev&&d.readiness<prev.readiness-1.5)parts.push('Readiness declining');
  if(d.tempo>2.5)parts.push('Ops tempo elevated');
  if(parts.length===0)parts.push('All metrics within range');
  det.textContent=parts.join(' · ');det.style.color=sc.text;

  const sS=mStatus(d.sleep,72,65),sR=mStatus(d.readiness,75,68),sA=mStatus(d.activity,80,65),sT=tStatus(d.tempo);
  document.getElementById('kSleep').textContent=d.sleep.toFixed(1);
  document.getElementById('kSleepSub').innerHTML=prev?`vs ${prev.m}: ${dStr(d.sleep,prev.sleep,1,'',true)}`:'First month';
  document.getElementById('kSleepBadge').innerHTML=mkBadge(sS);
  document.getElementById('kRead').textContent=d.readiness.toFixed(1);
  document.getElementById('kReadSub').innerHTML=prev?`vs ${prev.m}: ${dStr(d.readiness,prev.readiness,1,'',true)}`:'First month';
  document.getElementById('kReadBadge').innerHTML=mkBadge(sR);
  document.getElementById('kAct').textContent=d.activity.toFixed(1);
  document.getElementById('kActSub').innerHTML=prev?`vs ${prev.m}: ${dStr(d.activity,prev.activity,1,'',true)}`:'First month';
  document.getElementById('kActBadge').innerHTML=mkBadge(sA);
  document.getElementById('kTempo').textContent=d.tempo.toFixed(1)+'/5';
  document.getElementById('kTempoSub').textContent=tLabel(d.tempo);
  document.getElementById('kTempoBadge').innerHTML=mkBadge(sT);

  document.getElementById('sSteps').textContent=Math.round(d.steps).toLocaleString();
  document.getElementById('sStepsDelta').innerHTML=prev?dStr(d.steps,prev.steps,0,'',true):'';
  document.getElementById('sCals').textContent=Math.round(d.calories);
  document.getElementById('sCalsDelta').innerHTML=prev?dStr(d.calories,prev.calories,0,' kcal',true):'';
  document.getElementById('sSed').textContent=d.sed.toFixed(1)+'h';
  document.getElementById('sSedDelta').innerHTML=prev?dStr(d.sed,prev.sed,1,'h',false):'';
  document.getElementById('sTemp').textContent=(d.temp>=0?'+':'')+d.temp.toFixed(2)+'°C';
  document.getElementById('sTempDelta').innerHTML=prev?dStr(d.temp,prev.temp,2,'°C',false):'';

  document.getElementById('thPeriod').textContent=d.m;
  const rows=[
    {lbl:'Sleep score',v:d.sleep,pv:prev?.sleep,av:AVG12.sleep,dec:1,u:'',hg:true},
    {lbl:'Readiness score',v:d.readiness,pv:prev?.readiness,av:AVG12.readiness,dec:1,u:'',hg:true},
    {lbl:'Activity score',v:d.activity,pv:prev?.activity,av:AVG12.activity,dec:1,u:'',hg:true},
    {lbl:'Avg steps / day',v:d.steps,pv:prev?.steps,av:AVG12.steps,dec:0,u:'',hg:true},
    {lbl:'Active calories',v:d.calories,pv:prev?.calories,av:AVG12.calories,dec:0,u:'',hg:true},
    {lbl:'Sedentary hrs',v:d.sed,pv:prev?.sed,av:AVG12.sed,dec:1,u:'h',hg:false},
    {lbl:'Ops tempo',v:d.tempo,pv:prev?.tempo,av:AVG12.tempo,dec:1,u:'/5',hg:false},
  ];
  document.getElementById('cmpBody').innerHTML=rows.map(r=>{
    const pd=r.pv!=null?r.v-r.pv:null,ad=r.v-r.av;
    const ps=pd!=null?dStr(r.v,r.pv,r.dec,r.u,r.hg):'—';
    const as=dStr(r.v+ad,r.v+ad-(ad),r.dec,r.u,r.hg).replace(/\+0\.0|^\+0$/,'').trim()||`<span class="col-nu">${(ad>0?'+':'')+ad.toFixed(r.dec)}${r.u}</span>`;
    const adS=`<span class="${((ad>0&&r.hg)||(ad<0&&!r.hg))?'col-up':Math.abs(ad)<0.15?'col-nu':'col-dn'}">${ad>0?'+':''}${ad.toFixed(r.dec)}${r.u}</span>`;
    return`<tr><td>${r.lbl}</td><td class="num">${r.v.toFixed(r.dec)}${r.u}</td><td class="num">${ps}</td><td class="num">${adS}</td><td style="font-size:10px">${dirStr(pd,r.hg)}</td></tr>`;
  }).join('');

  const note=getNote(d,prev,s);
  document.getElementById('cmdNote').style.cssText=`background:${sc.bg};border-left:3px solid ${sc.dot};border-radius:var(--radius);padding:12px 14px;margin-bottom:16px`;
  document.getElementById('cmdNoteHd').style.color=sc.text;
  document.getElementById('cmdNoteHd').textContent=note.head;
  document.getElementById('cmdNoteBody').innerHTML=`<strong>Risk:</strong> ${note.risk}.<br><strong>Recommended action:</strong> ${note.rec}`;

  highlightMonth(i);
}

buildCharts();
updateDash();
</script>
</body></html>
