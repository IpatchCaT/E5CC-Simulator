<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>E5CC Temperature Controller Simulator</title>
<style>
  :root {
    --bg:#15181b; --panel:#1f2428; --panel2:#272d32; --line:#39414a; --text:#e4e9ee; --muted:#93a0ab;
    --accent:#2f81f7; --good:#39d27a; --bad:#ff5a4f; --warn:#f2b230; --focus:#8ab4f8;
  }
  * { box-sizing:border-box; }
  body { margin:0; background:var(--bg); color:var(--text); font-family:"Segoe UI",Arial,sans-serif; font-size:14px; }
  header { padding:12px 20px; background:#0f1215; border-bottom:1px solid var(--line); display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:8px; }
  header h1 { margin:0; font-size:17px; font-weight:600; }
  header small { color:var(--muted); }
  .pill { display:inline-block; padding:2px 10px; border-radius:10px; font-size:12px; background:var(--panel2); border:1px solid var(--line); }
  .pill.good { color:var(--good); border-color:var(--good); } .pill.bad { color:var(--bad); border-color:var(--bad); } .pill.warn { color:var(--warn); border-color:var(--warn); }
  #banner { display:none; margin:10px 20px 0; padding:9px 14px; border-radius:6px; font-weight:600; }
  #banner.info { display:block; background:#10263f; color:#9cc8ff; border:1px solid #1f4a7a; }
  #banner.ok { display:block; background:#0f2e1c; color:#7ff0ac; border:1px solid #1c6b3d; }
  #banner.err { display:block; background:#3a1311; color:#ff9a92; border:1px solid #8a2b25; }
  main { display:grid; grid-template-columns:minmax(0,1.15fr) minmax(0,1fr); gap:16px; padding:16px 20px 40px; max-width:1400px; margin:0 auto; }
  @media (max-width:950px) { main { grid-template-columns:1fr; } }
  .card { background:var(--panel); border:1px solid var(--line); border-radius:10px; padding:14px; margin-bottom:16px; }
  .card h2 { margin:0 0 10px; font-size:14px; letter-spacing:.04em; text-transform:uppercase; color:var(--muted); font-weight:600; }

  /* controller face */
  .device { background:linear-gradient(160deg,#30363c,#1b1f23); border:2px solid #4a535c; border-radius:14px; padding:16px; max-width:520px; margin:0 auto 4px; box-shadow:0 8px 24px rgba(0,0,0,.5), inset 0 1px 0 rgba(255,255,255,.08); }
  .devhead { display:flex; justify-content:space-between; font-size:11px; color:#aeb8c1; letter-spacing:.1em; margin-bottom:8px; }
  .screen { background:#050607; border:2px solid #000; border-radius:6px; padding:12px 14px; box-shadow:inset 0 0 14px #000; }
  .dispRow { display:flex; align-items:center; justify-content:space-between; gap:10px; }
  .dispLabel { font-size:11px; letter-spacing:.12em; width:34px; }
  .pv { --led:#ff3b2f; --ghost:#2b0e0c; } .sv { --led:#38ff7c; --ghost:#0b2514; } .tm { --led:#ffb02e; --ghost:#2a1d08; }
  svg.seg7 { display:block; }
  .seg { fill:var(--ghost); }
  .seg.on, .dp.on, .col.on { fill:var(--led); filter:drop-shadow(0 0 3px var(--led)); }
  .dp, .col { fill:var(--ghost); }
  .leds { display:flex; gap:14px; margin-top:10px; flex-wrap:wrap; }
  .ind { font-size:11px; letter-spacing:.08em; display:flex; align-items:center; gap:5px; color:#6c7782; }
  .ind i { width:10px; height:10px; border-radius:50%; background:#2a2f34; display:inline-block; border:1px solid #000; }
  .ind.on { color:#e8eef3; }
  .ind.on.g i { background:#38ff7c; box-shadow:0 0 8px #38ff7c; }
  .ind.on.o i { background:#ffb02e; box-shadow:0 0 8px #ffb02e; }
  .ind.on.r i { background:#ff3b2f; box-shadow:0 0 8px #ff3b2f; }
  .keys { display:grid; grid-template-columns:repeat(4,1fr); gap:10px; margin-top:14px; }
  .key { font:inherit; font-size:12px; font-weight:600; letter-spacing:.06em; padding:12px 0; color:#dfe6ec; background:linear-gradient(#444c54,#2c3237); border:1px solid #11151a; border-bottom-width:3px; border-radius:7px; cursor:pointer; user-select:none; touch-action:manipulation; }
  .key:active { transform:translateY(2px); border-bottom-width:1px; }
  .runrow { display:flex; gap:10px; margin-top:12px; }
  .runbtn { flex:1; font:inherit; font-size:16px; font-weight:700; letter-spacing:.08em; padding:14px 0; border-radius:8px; border:1px solid #000; cursor:pointer; color:#fff; }
  #btnStart { background:#1f8f4e; } #btnStop { background:#b3332b; }
  .runbtn:disabled { opacity:.4; cursor:not-allowed; }
  .status { margin-top:10px; display:flex; flex-wrap:wrap; gap:8px; font-size:12px; color:var(--muted); }

  /* controls */
  label { display:inline-flex; align-items:center; gap:6px; margin:3px 10px 3px 0; }
  input[type=number], input[type=text], select { font:inherit; padding:6px 8px; background:#12161a; color:var(--text); border:1px solid var(--line); border-radius:5px; }
  input[type=number] { width:84px; }
  input[type=text].wide { width:100%; }
  button.btn { font:inherit; padding:7px 13px; border-radius:5px; border:1px solid var(--accent); background:var(--accent); color:#fff; cursor:pointer; margin:3px 6px 3px 0; }
  button.btn.alt { background:transparent; border-color:var(--line); color:var(--text); }
  button.btn.danger { background:transparent; border-color:var(--bad); color:var(--bad); }
  button:focus-visible, input:focus-visible, select:focus-visible { outline:2px solid var(--focus); outline-offset:2px; }
  .row { margin-bottom:8px; }
  .hint { color:var(--muted); font-size:12px; margin:6px 0 0; }
  .timerBox { display:flex; align-items:center; gap:12px; background:#050607; border:2px solid #000; border-radius:6px; padding:8px 12px; margin-bottom:8px; }
  canvas { width:100%; height:240px; display:block; background:#0b0e10; border:1px solid var(--line); border-radius:6px; }
  .wrap { max-height:230px; overflow:auto; border:1px solid var(--line); border-radius:6px; }
  table { border-collapse:collapse; width:100%; font-size:12px; }
  th { position:sticky; top:0; background:var(--panel2); text-align:left; padding:5px 8px; }
  td { padding:4px 8px; border-top:1px solid var(--line); vertical-align:top; }
  .ok { color:var(--good); } .qd { color:var(--warn); } .lo { color:var(--muted); } .er { color:var(--bad); }
</style>
</head>
<body>

<header>
  <div><h1>E5CC Digital Temperature Controller &mdash; Training Simulator</h1><small>Independent training tool. Not affiliated with or endorsed by Omron.</small></div>
  <div><span class="pill" id="pillState">STOP</span> <span class="pill" id="pillPA">Power Automate: not set</span> <span class="pill" id="pillRows">Rows: 0</span></div>
</header>
<div id="banner" role="status"></div>

<main>
<div>
  <!-- CONTROLLER FACE -->
  <div class="card">
    <div class="device">
      <div class="devhead"><span>E5CC &bull; TEMP CONTROLLER</span><span id="devId">UNIT-01</span></div>
      <div class="screen">
        <div class="dispRow"><span class="dispLabel" style="color:#ff6a60" id="lblUp">PV</span><div id="dispPV" class="pv"></div></div>
        <div class="dispRow" style="margin-top:8px"><span class="dispLabel" style="color:#6dff9f" id="lblLow">SV</span><div id="dispSV" class="sv"></div></div>
        <div class="leds">
          <span class="ind r" id="ledOUT1"><i></i>OUT1</span>
          <span class="ind o" id="ledSUB1"><i></i>SUB1</span>
          <span class="ind g" id="ledCMW"><i></i>CMW</span>
          <span class="ind o" id="ledSTOP"><i></i>STOP</span>
          <span class="ind g" id="ledRUN"><i></i>RUN</span>
          <span class="ind o" id="ledSOAK"><i></i>SOAK</span>
        </div>
      </div>
      <div class="keys">
        <button class="key" id="keyLevel" title="Back to operation display">LEVEL</button>
        <button class="key" id="keyMode" title="Next parameter">MODE</button>
        <button class="key" id="keyUp" title="Increase">&#9650;</button>
        <button class="key" id="keyDown" title="Decrease">&#9660;</button>
      </div>
      <div class="runrow">
        <button class="runbtn" id="btnStart">START</button>
        <button class="runbtn" id="btnStop" disabled>STOP</button>
      </div>
      <div class="status"><span id="txtSession">Session: -</span><span id="txtElapsed">Elapsed: 00:00</span><span id="txtOut">Output: 0.0 %</span></div>
    </div>
    <p class="hint" style="text-align:center">MODE cycles AL-1 / P / I / d. &#9650;&#9660; edit the shown value (SV on the main screen). Hold for fast change. Keyboard: Up/Down arrows change SV.</p>
  </div>

  <div class="card"><h2>Live trend</h2><canvas id="chart"></canvas></div>

  <div class="card">
    <h2>Event log (parameter changes, runs, alarms, exports)</h2>
    <div class="wrap"><table><thead><tr><th>Time</th><th>Event</th><th>Detail</th></tr></thead><tbody id="evBody"></tbody></table></div>
  </div>
</div>

<div>
  <div class="card">
    <h2>Set value (SV)</h2>
    <div class="row"><label>SV (&deg;C) <input type="number" id="svInput" value="100" min="0" max="300" step="0.1"></label>
      <button class="btn" id="btnSetSv">Set SV</button>
      <button class="btn alt" id="btnSvDown">-10</button><button class="btn alt" id="btnSvUp">+10</button></div>
  </div>

  <div class="card">
    <h2>Temperature duration timer</h2>
    <div class="timerBox"><div id="dispTimer" class="tm"></div><span id="txtTimer" class="pill">Idle</span></div>
    <div class="row">
      <label><input type="checkbox" id="chkTimer" checked> Use timer</label>
      <label>Min <input type="number" id="timerMin" value="2" min="0" max="99"></label>
      <label>Sec <input type="number" id="timerSec" value="0" min="0" max="59"></label>
      <button class="btn" id="btnSetTimer">Set timer</button>
    </div>
    <div class="row">
      <label>Starts counting
        <select id="timerMode"><option value="start">when START is pressed</option><option value="band">when PV reaches SV band</option></select></label>
      <label>Band &plusmn;&deg;C <input type="number" id="bandInput" value="2" min="0.1" max="20" step="0.1"></label>
    </div>
    <div class="row">
      <label><input type="checkbox" id="chkAutoStop" checked> Auto-stop at end</label>
      <label><input type="checkbox" id="chkAutoExport" checked> Auto-export CSV at end</label>
    </div>
  </div>

  <div class="card">
    <h2>Parameters &amp; alarm</h2>
    <div class="row">
      <label>AL-1 high alarm (&deg;C) <input type="number" id="al1Input" value="250" step="1"></label>
      <label>P band (&deg;C) <input type="number" id="pInput" value="8" step="0.1" min="0.1"></label>
      <label>I (s) <input type="number" id="iInput" value="233" step="1" min="0"></label>
      <label>d (s) <input type="number" id="dInput" value="40" step="1" min="0"></label>
    </div>
    <div class="row"><label><input type="checkbox" id="chkMute"> Mute alarm sound</label></div>
  </div>

  <div class="card">
    <h2>Simulation</h2>
    <div class="row">
      <label>Speed <select id="speedSel"><option value="1">1x (real time)</option><option value="5" selected>5x</option><option value="10">10x</option><option value="20">20x</option></select></label>
      <label>Ambient (&deg;C) <input type="number" id="ambInput" value="25" step="1"></label>
      <label>Noise (&deg;C) <input type="number" id="noiseInput" value="0.1" step="0.05" min="0"></label>
    </div>
    <button class="btn alt" id="btnCool">Reset plant to ambient</button>
  </div>

  <div class="card">
    <h2>Export session data</h2>
    <div class="row">
      <button class="btn" id="btnExportCsv">Export CSV</button>
      <button class="btn" id="btnExportXlsx">Export Excel (.xlsx)</button>
      <button class="btn alt" id="btnExportEvents">Export events CSV</button>
      <button class="btn danger" id="btnClearData">Clear data</button>
    </div>
    <p class="hint">Every export downloads a file and also sends an "export" event to Power Automate.</p>
  </div>

  <div class="card">
    <h2>Power Automate connection</h2>
    <div class="row"><input type="text" class="wide" id="paUrl" placeholder="Paste the HTTP POST URL from 'When an HTTP request is received'"></div>
    <div class="row">
      <label>Device ID <input type="text" id="deviceId" value="UNIT-01" style="width:110px"></label>
      <label>Send telemetry every <input type="number" id="paInterval" value="5" min="1" max="600"> s</label>
    </div>
    <div class="row">
      <label><input type="checkbox" id="chkCsvPayload" checked> Include CSV text in export events</label>
      <label>Send as <select id="paMode"><option value="plain">text/plain (no CORS block)</option><option value="json">application/json (needs CORS)</option></select></label>
    </div>
    <div class="row">
      <button class="btn" id="btnTestPA">Send test event</button>
      <button class="btn alt" id="btnFlush">Send queued (<span id="qCount">0</span>)</button>
      <button class="btn danger" id="btnClearPA">Clear send log</button>
    </div>
    <div class="wrap"><table><thead><tr><th>Time</th><th>Event</th><th>Result</th></tr></thead><tbody id="paBody"></tbody></table></div>
    <p class="hint">Note: hosted pages block requests to other sites, so live posting to Power Automate only works when you run the downloaded HTML file locally; here events are queued. Sent = request left the browser. The browser cannot read Power Automate's reply, so confirm runs in the flow's run history.</p>
  </div>
</div>
</main>

<script>
(function () {
  var $ = function (id) { return document.getElementById(id); };
  function clamp(v, a, b) { return Math.max(a, Math.min(b, v)); }
  function r1(v) { return Math.round(v * 10) / 10; }
  function pad(n) { return String(n).padStart(2, "0"); }
  function esc(s) { return String(s).replace(/[&<>"]/g, function (c) { return {"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]; }); }
  function fmtTs(d) { return d.getFullYear() + "-" + pad(d.getMonth()+1) + "-" + pad(d.getDate()) + " " + pad(d.getHours()) + ":" + pad(d.getMinutes()) + ":" + pad(d.getSeconds()); }
  function fileStamp(d) { return d.getFullYear() + pad(d.getMonth()+1) + pad(d.getDate()) + "_" + pad(d.getHours()) + pad(d.getMinutes()) + pad(d.getSeconds()); }
  function mmss(sec) { sec = Math.max(0, Math.round(sec)); return pad(Math.floor(sec / 60)) + ":" + pad(sec % 60); }

  /*SIM_START*/
  var PMAX = 1.8, KLOSS = 0.006;   // heater power (C/s at 100%) and heat-loss coefficient (1/s)
  function simStep(s, prm, sv, run, dt, amb) {
    var n = Math.max(1, Math.ceil(dt / 0.5)), h = dt / n, u = 0;
    for (var k = 0; k < n; k++) {
      var pv = s.T;
      if (run) {
        var e = sv - pv;
        if (Math.abs(e) < prm.p * 3) s.ie += e * h;       // integrate only near the setpoint (anti-windup)
        var imax = prm.p * prm.i; if (s.ie > imax) s.ie = imax; if (s.ie < 0) s.ie = 0;
        s.dm = 0.8 * s.dm + 0.2 * ((pv - s.pvPrev) / h);  // filtered rate of PV
        var out = (100 / prm.p) * (e + (prm.i > 0 ? s.ie / prm.i : 0) - prm.d * s.dm);
        u = clamp(out, 0, 100);
      } else { s.ie = 0; u = 0; }
      s.pvPrev = pv;
      s.T += (PMAX * u / 100 - KLOSS * (s.T - amb)) * h;
    }
    s.u = u; return s;
  }
  /*SIM_END*/

  /*XLSX_START*/
  var CRC_T = (function () { var t = [], c, n, k; for (n = 0; n < 256; n++) { c = n; for (k = 0; k < 8; k++) c = c & 1 ? 0xEDB88320 ^ (c >>> 1) : c >>> 1; t[n] = c >>> 0; } return t; })();
  function crc32(b) { var c = 0xFFFFFFFF; for (var i = 0; i < b.length; i++) c = CRC_T[(c ^ b[i]) & 255] ^ (c >>> 8); return (c ^ 0xFFFFFFFF) >>> 0; }
  function utf8(s) { return new TextEncoder().encode(s); }
  function zipStore(files) {
    var d = new Date(), time = (d.getHours() << 11) | (d.getMinutes() << 5) | (d.getSeconds() >> 1), date = ((d.getFullYear() - 1980) << 9) | ((d.getMonth() + 1) << 5) | d.getDate();
    var parts = [], central = [], offset = 0;
    files.forEach(function (f) {
      var name = utf8(f.name), data = f.data, crc = crc32(data);
      var lh = new DataView(new ArrayBuffer(30));
      lh.setUint32(0, 0x04034b50, true); lh.setUint16(4, 20, true); lh.setUint16(6, 0, true); lh.setUint16(8, 0, true);
      lh.setUint16(10, time, true); lh.setUint16(12, date, true); lh.setUint32(14, crc, true);
      lh.setUint32(18, data.length, true); lh.setUint32(22, data.length, true); lh.setUint16(26, name.length, true); lh.setUint16(28, 0, true);
      parts.push(new Uint8Array(lh.buffer), name, data);
      var ch = new DataView(new ArrayBuffer(46));
      ch.setUint32(0, 0x02014b50, true); ch.setUint16(4, 20, true); ch.setUint16(6, 20, true); ch.setUint16(8, 0, true); ch.setUint16(10, 0, true);
      ch.setUint16(12, time, true); ch.setUint16(14, date, true); ch.setUint32(16, crc, true);
      ch.setUint32(20, data.length, true); ch.setUint32(24, data.length, true); ch.setUint16(28, name.length, true);
      ch.setUint32(42, offset, true);
      central.push(new Uint8Array(ch.buffer), name);
      offset += 30 + name.length + data.length;
    });
    var csize = central.reduce(function (a, b) { return a + b.length; }, 0);
    var end = new DataView(new ArrayBuffer(22));
    end.setUint32(0, 0x06054b50, true); end.setUint16(8, files.length, true); end.setUint16(10, files.length, true);
    end.setUint32(12, csize, true); end.setUint32(16, offset, true);
    var all = parts.concat(central, [new Uint8Array(end.buffer)]), total = all.reduce(function (a, b) { return a + b.length; }, 0);
    var out = new Uint8Array(total), p = 0; all.forEach(function (b) { out.set(b, p); p += b.length; });
    return out;
  }
  function xmlEsc(s) { return String(s).replace(/[\u0000-\u0008\u000b\u000c\u000e-\u001f]/g, "").replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;"); }
  function colLetter(n) { var s = ""; n++; while (n > 0) { var m = (n - 1) % 26; s = String.fromCharCode(65 + m) + s; n = Math.floor((n - 1) / 26); } return s; }
  function sheetXml(rows, widths) {
    var x = '<?xml version="1.0" encoding="UTF-8" standalone="yes"?><worksheet xmlns="http://schemas.openxmlformats.org/spreadsheetml/2006/main">';
    if (widths) x += "<cols>" + widths.map(function (w, i) { return '<col min="' + (i + 1) + '" max="' + (i + 1) + '" width="' + w + '" customWidth="1"/>'; }).join("") + "</cols>";
    x += "<sheetData>";
    rows.forEach(function (r, ri) {
      x += '<row r="' + (ri + 1) + '">';
      r.forEach(function (v, ci) {
        var ref = colLetter(ci) + (ri + 1), st = ri === 0 ? ' s="1"' : "";
        if (typeof v === "number" && isFinite(v)) x += '<c r="' + ref + '"' + st + "><v>" + v + "</v></c>";
        else x += '<c r="' + ref + '"' + st + ' t="inlineStr"><is><t xml:space="preserve">' + xmlEsc(v == null ? "" : v) + "</t></is></c>";
      });
      x += "</row>";
    });
    return x + "</sheetData></worksheet>";
  }
  function buildXlsx(sheets) {
    var H = '<?xml version="1.0" encoding="UTF-8" standalone="yes"?>', NS = "http://schemas.openxmlformats.org/";
    var files = [];
    files.push({ name: "[Content_Types].xml", data: utf8(H + '<Types xmlns="' + NS + 'package/2006/content-types"><Default Extension="rels" ContentType="application/vnd.openxmlformats-package.relationships+xml"/><Default Extension="xml" ContentType="application/xml"/><Override PartName="/xl/workbook.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.sheet.main+xml"/><Override PartName="/xl/styles.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.styles+xml"/>' +
      sheets.map(function (s, i) { return '<Override PartName="/xl/worksheets/sheet' + (i + 1) + '.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.worksheet+xml"/>'; }).join("") + "</Types>") });
    files.push({ name: "_rels/.rels", data: utf8(H + '<Relationships xmlns="' + NS + 'package/2006/relationships"><Relationship Id="rId1" Type="' + NS + 'officeDocument/2006/relationships/officeDocument" Target="xl/workbook.xml"/></Relationships>') });
    files.push({ name: "xl/workbook.xml", data: utf8(H + '<workbook xmlns="' + NS + 'spreadsheetml/2006/main" xmlns:r="' + NS + 'officeDocument/2006/relationships"><sheets>' +
      sheets.map(function (s, i) { return '<sheet name="' + xmlEsc(s.name) + '" sheetId="' + (i + 1) + '" r:id="rId' + (i + 1) + '"/>'; }).join("") + "</sheets></workbook>") });
    files.push({ name: "xl/_rels/workbook.xml.rels", data: utf8(H + '<Relationships xmlns="' + NS + 'package/2006/relationships">' +
      sheets.map(function (s, i) { return '<Relationship Id="rId' + (i + 1) + '" Type="' + NS + 'officeDocument/2006/relationships/worksheet" Target="worksheets/sheet' + (i + 1) + '.xml"/>'; }).join("") +
      '<Relationship Id="rId' + (sheets.length + 1) + '" Type="' + NS + 'officeDocument/2006/relationships/styles" Target="styles.xml"/></Relationships>') });
    files.push({ name: "xl/styles.xml", data: utf8(H + '<styleSheet xmlns="' + NS + 'spreadsheetml/2006/main"><fonts count="2"><font><sz val="11"/><name val="Calibri"/></font><font><b/><sz val="11"/><name val="Calibri"/></font></fonts><fills count="2"><fill><patternFill patternType="none"/></fill><fill><patternFill patternType="gray125"/></fill></fills><borders count="1"><border><left/><right/><top/><bottom/><diagonal/></border></borders><cellStyleXfs count="1"><xf numFmtId="0" fontId="0" fillId="0" borderId="0"/></cellStyleXfs><cellXfs count="2"><xf numFmtId="0" fontId="0" fillId="0" borderId="0" xfId="0"/><xf numFmtId="0" fontId="1" fillId="0" borderId="0" xfId="0" applyFont="1"/></cellXfs><cellStyles count="1"><cellStyle name="Normal" xfId="0" builtinId="0"/></cellStyles></styleSheet>') });
    sheets.forEach(function (s, i) { files.push({ name: "xl/worksheets/sheet" + (i + 1) + ".xml", data: utf8(sheetXml(s.rows, s.widths)) }); });
    return zipStore(files);
  }
  /*XLSX_END*/

  // ---------- state ----------
  var cfg = { url: "", deviceId: "UNIT-01", interval: 5, csvPayload: true, mode: "plain" };
  var prm = { p: 8, i: 233, d: 40, al1: 250 };
  var S = { sv: 100, pv: 25, run: false, u: 0, alarm: false, sessionId: "-", elapsed: 0, soaking: false };
  var plant = { T: 25, ie: 0, dm: 0, pvPrev: 25, u: 0 };
  var T = { setSec: 120, remaining: 120, state: "idle" };
  var rows = [], events = [], chartBuf = [], paLog = [], queue = [];
  var paCount = { sent: 0, local: 0 };
  var menuIdx = 0, menuTimer = null, audioCtx = null, bannerTimer = null;

  function banner(msg, kind, ms) {
    var b = $("banner"); b.textContent = msg; b.className = kind || "info";
    clearTimeout(bannerTimer); bannerTimer = setTimeout(function () { b.className = ""; b.style.display = ""; }, ms || 6000);
  }
  function beep(freq, dur, times) {
    if ($("chkMute").checked) return;
    try {
      audioCtx = audioCtx || new (window.AudioContext || window.webkitAudioContext)();
      for (var i = 0; i < (times || 1); i++) {
        var o = audioCtx.createOscillator(), g = audioCtx.createGain(), t0 = audioCtx.currentTime + i * (dur + 0.12);
        o.frequency.value = freq; g.gain.value = 0.08; o.connect(g); g.connect(audioCtx.destination); o.start(t0); o.stop(t0 + dur);
      }
    } catch (e) {}
  }

  // ---------- 7-segment displays ----------
  var SEGMAP = { "0":"abcdef","1":"bc","2":"abdeg","3":"abcdg","4":"bcfg","5":"acdfg","6":"acdefg","7":"abc","8":"abcdefg","9":"abcdfg","-":"g"," ":"",
    "A":"abcefg","b":"cdefg","C":"adef","d":"bcdeg","E":"adefg","F":"aefg","H":"bcefg","I":"ef","L":"def","n":"ceg","o":"cdeg","P":"abefg","r":"eg","S":"acdfg","t":"defg","U":"bcdef" };
  var POLY = { a:"10,4 40,4 35,10 15,10", b:"43,6 43,42 38,37 38,11", c:"43,48 43,84 38,79 38,53", d:"10,86 40,86 35,80 15,80", e:"7,48 7,84 12,79 12,53", f:"7,6 7,42 12,37 12,11", g:"10,45 15,40 35,40 40,45 35,50 15,50" };
  function SevenSeg(host, n, opts) {
    opts = opts || {}; var NS = "http://www.w3.org/2000/svg", w = 54, gap = 4, colW = opts.colon ? 16 : 0;
    var svg = document.createElementNS(NS, "svg"); svg.setAttribute("class", "seg7");
    var total = n * w + (n - 1) * gap + colW, scale = opts.scale || 1;
    svg.setAttribute("viewBox", "0 0 " + total + " 90"); svg.setAttribute("width", total * scale); svg.setAttribute("height", 90 * scale);
    var digits = [], x = 0;
    for (var i = 0; i < n; i++) {
      var g = document.createElementNS(NS, "g"); g.setAttribute("transform", "translate(" + x + ",0)"); var segs = {};
      "abcdefg".split("").forEach(function (k) { var p = document.createElementNS(NS, "polygon"); p.setAttribute("points", POLY[k]); p.setAttribute("class", "seg"); g.appendChild(p); segs[k] = p; });
      var dp = document.createElementNS(NS, "circle"); dp.setAttribute("cx", 49); dp.setAttribute("cy", 84); dp.setAttribute("r", 3); dp.setAttribute("class", "dp"); g.appendChild(dp);
      svg.appendChild(g); digits.push({ segs: segs, dp: dp }); x += w + gap;
      if (opts.colon && i === 1) {
        [30, 60].forEach(function (cy) { var c = document.createElementNS(NS, "circle"); c.setAttribute("cx", x + 4); c.setAttribute("cy", cy); c.setAttribute("r", 3.5); c.setAttribute("class", "col on"); svg.appendChild(c); });
        x += colW;
      }
    }
    host.appendChild(svg);
    return { set: function (str, left) {
      var cells = [];
      String(str).split("").forEach(function (ch) { if (ch === "." && cells.length) cells[cells.length - 1].dp = true; else cells.push({ c: ch, dp: false }); });
      cells = cells.slice(0, n);
      while (cells.length < n) { if (left) cells.push({ c: " ", dp: false }); else cells.unshift({ c: " ", dp: false }); }
      cells.forEach(function (cell, i) {
        var on = SEGMAP[cell.c] || "";
        "abcdefg".split("").forEach(function (k) { digits[i].segs[k].setAttribute("class", "seg" + (on.indexOf(k) >= 0 ? " on" : "")); });
        digits[i].dp.setAttribute("class", "dp" + (cell.dp ? " on" : ""));
      });
    } };
  }
  var dPV = SevenSeg($("dispPV"), 4, { scale: 0.95 }), dSV = SevenSeg($("dispSV"), 4, { scale: 0.95 }), dTM = SevenSeg($("dispTimer"), 4, { scale: 0.55, colon: true });
  function fmtNum(v) { return (Math.abs(v) >= 1000 || v <= -100) ? String(Math.round(v)) : r1(v).toFixed(1); }

  // ---------- menu / keys ----------
  var ITEMS = [
    { k: "sv", label: "" },
    { k: "al1", label: "AL-1", step: 1, min: -100, max: 400, fmt: fmtNum },
    { k: "p", label: "P", step: 0.1, min: 0.1, max: 99.9, fmt: fmtNum },
    { k: "i", label: "I", step: 1, min: 0, max: 999, fmt: function (v) { return String(Math.round(v)); } },
    { k: "d", label: "d", step: 1, min: 0, max: 999, fmt: function (v) { return String(Math.round(v)); } }
  ];
  function touchMenu() { clearTimeout(menuTimer); if (menuIdx > 0) menuTimer = setTimeout(function () { menuIdx = 0; refreshDisplays(); }, 8000); }
  function refreshDisplays() {
    if (menuIdx === 0) { dPV.set(fmtNum(S.pv)); dSV.set(fmtNum(S.sv)); $("lblUp").textContent = "PV"; $("lblLow").textContent = "SV"; }
    else { var it = ITEMS[menuIdx]; dPV.set(it.label, true); dSV.set(it.fmt(prm[it.k])); $("lblUp").textContent = "PAR"; $("lblLow").textContent = "VAL"; }
  }
  $("keyMode").onclick = function () { menuIdx = (menuIdx + 1) % ITEMS.length; touchMenu(); refreshDisplays(); };
  $("keyLevel").onclick = function () { menuIdx = 0; refreshDisplays(); };

  var pending = {};
  function commit(key, label, oldV, newV) {
    clearTimeout(pending[key] && pending[key].t);
    if (!pending[key]) pending[key] = { old: oldV };
    pending[key].t = setTimeout(function () {
      var o = pending[key].old; delete pending[key];
      if (o !== newV) ev(key === "sv" ? "sv_change" : "param_change", label + ": " + o + " -> " + newV, { parameter: label, old: o, "new": newV });
    }, 800);
  }
  function setSV(v, src) {
    v = clamp(Math.round(v * 10) / 10, 0, 300);
    if (v === S.sv) return;
    commit("sv", "SV (" + (src || "key") + ")", S.sv, v);
    S.sv = v; $("svInput").value = v; refreshDisplays();
  }
  function setParam(k, v) {
    var it = ITEMS.filter(function (x) { return x.k === k; })[0];
    v = clamp(Math.round(v * 10) / 10, it.min, it.max);
    if (v === prm[k]) return;
    commit("p_" + k, it.label, prm[k], v);
    prm[k] = v; syncParamInputs(); refreshDisplays();
  }
  function syncParamInputs() { $("al1Input").value = prm.al1; $("pInput").value = prm.p; $("iInput").value = prm.i; $("dInput").value = prm.d; }
  function stepCurrent(dir, mult) {
    if (menuIdx === 0) setSV(S.sv + dir * 0.1 * (mult || 1), "key");
    else { var it = ITEMS[menuIdx]; setParam(it.k, prm[it.k] + dir * it.step * (mult || 1)); touchMenu(); }
  }
  function holdKey(btn, dir) {
    var t1, t2, t0;
    function stop() { clearTimeout(t1); clearInterval(t2); }
    btn.addEventListener("pointerdown", function (e) {
      e.preventDefault(); t0 = Date.now(); stepCurrent(dir, menuIdx === 0 ? 10 : 1);
      t1 = setTimeout(function () { t2 = setInterval(function () { var fast = Date.now() - t0 > 2000; stepCurrent(dir, menuIdx === 0 ? (fast ? 100 : 10) : (fast ? 5 : 1)); }, 100); }, 400);
    });
    ["pointerup", "pointerleave", "pointercancel"].forEach(function (n) { btn.addEventListener(n, stop); });
    btn.addEventListener("keydown", function (e) { if (e.key === "Enter" || e.key === " ") { e.preventDefault(); stepCurrent(dir, menuIdx === 0 ? 10 : 1); } });
  }
  holdKey($("keyUp"), 1); holdKey($("keyDown"), -1);
  document.addEventListener("keydown", function (e) {
    var tag = (e.target.tagName || "").toLowerCase();
    if (tag === "input" || tag === "select" || tag === "button") return;
    if (e.key === "ArrowUp") { e.preventDefault(); stepCurrent(1, menuIdx === 0 ? 10 : 1); }
    if (e.key === "ArrowDown") { e.preventDefault(); stepCurrent(-1, menuIdx === 0 ? 10 : 1); }
  });
  $("btnSetSv").onclick = function () { var v = parseFloat($("svInput").value); if (isNaN(v)) { banner("Enter a valid SV.", "err"); return; } setSV(v, "panel"); };
  $("svInput").addEventListener("keydown", function (e) { if (e.key === "Enter") $("btnSetSv").click(); });
  $("btnSvUp").onclick = function () { setSV(S.sv + 10, "panel"); };
  $("btnSvDown").onclick = function () { setSV(S.sv - 10, "panel"); };
  [["al1Input","al1"],["pInput","p"],["iInput","i"],["dInput","d"]].forEach(function (m) {
    $(m[0]).onchange = function () { var v = parseFloat(this.value); if (isNaN(v)) { syncParamInputs(); return; } setParam(m[1], v); };
  });

  // ---------- events + Power Automate ----------
  function renderEvents() {
    $("evBody").innerHTML = events.slice(-100).reverse().map(function (e) { return "<tr><td>" + fmtTs(e.ts) + "</td><td>" + esc(e.type) + "</td><td>" + esc(e.detail) + "</td></tr>"; }).join("") || '<tr><td colspan="3" class="lo">No events yet.</td></tr>';
  }
  function ev(type, detail, extra) { events.push({ ts: new Date(), type: type, detail: detail }); renderEvents(); sendPA(type, Object.assign({ detail: detail }, extra || {})); }
  function renderPA() {
    $("paBody").innerHTML = paLog.slice(0, 60).map(function (e) { var c = e.res === "Sent" ? "ok" : e.res === "Queued" ? "qd" : e.res.indexOf("Local") === 0 ? "lo" : "er"; return "<tr><td>" + e.time + "</td><td>" + esc(e.type) + '</td><td class="' + c + '">' + esc(e.res) + "</td></tr>"; }).join("");
    $("qCount").textContent = queue.length;
    var pill = $("pillPA");
    if (!cfg.url) { pill.textContent = "Power Automate: not set (local only)"; pill.className = "pill warn"; }
    else if (queue.length) { pill.textContent = "Power Automate: " + queue.length + " queued"; pill.className = "pill bad"; }
    else { pill.textContent = "Power Automate: connected (" + paCount.sent + " sent)"; pill.className = "pill good"; }
  }
  function blinkCMW() { $("ledCMW").classList.add("on"); setTimeout(function () { $("ledCMW").classList.remove("on"); }, 350); }
  function post(payload) {
    var plain = cfg.mode === "plain";
    return fetch(cfg.url, { method: "POST", mode: plain ? "no-cors" : "cors", headers: { "Content-Type": plain ? "text/plain" : "application/json" }, body: JSON.stringify(payload) });
  }
  function sendPA(type, extra) {
    var payload = Object.assign({ schema: "e5cc.v1", event: type, deviceId: cfg.deviceId, sessionId: S.sessionId, ts: new Date().toISOString(),
      pv: r1(S.pv), sv: S.sv, outputPct: r1(S.u), state: S.run ? "RUN" : "STOP", alarm: S.alarm, timerState: T.state, remainingSec: Math.round(T.remaining),
      params: { p: prm.p, i: prm.i, d: prm.d, al1: prm.al1 } }, extra || {});
    var entry = { time: fmtTs(new Date()).slice(11), type: type, res: "Local" };
    paLog.unshift(entry);
    if (!cfg.url) { paCount.local++; entry.res = "Local only (no URL)"; renderPA(); return; }
    blinkCMW();
    if (!navigator.onLine) { entry.res = "Queued"; queue.push(payload); renderPA(); return; }
    post(payload).then(function () { entry.res = "Sent"; paCount.sent++; renderPA(); }, function () { entry.res = "Queued"; queue.push(payload); if (queue.length > 500) queue.shift(); renderPA(); });
    renderPA();
  }
  $("btnFlush").onclick = function () {
    if (!cfg.url) { banner("Paste the Power Automate URL first.", "err"); return; }
    if (!queue.length) { banner("Nothing queued.", "info", 2500); return; }
    var q = queue.splice(0, queue.length), ok = 0;
    q.reduce(function (p, item) {
      return p.then(function () { return post(item).then(function () { ok++; paCount.sent++; }, function () { queue.push(item); }); });
    }, Promise.resolve()).then(function () { paLog.unshift({ time: fmtTs(new Date()).slice(11), type: "flush_queue", res: ok + " sent, " + queue.length + " still queued" }); renderPA(); banner(ok + " queued event(s) sent.", ok ? "ok" : "err", 3500); });
  };
  $("btnTestPA").onclick = function () {
    if (!cfg.url) { banner("Paste the Power Automate URL first, then send a test event.", "err"); return; }
    ev("test", "Test event from simulator");
    banner("Test event sent. Check the flow's run history in Power Automate.", "info");
  };
  $("btnClearPA").onclick = function () { paLog = []; queue = []; paCount = { sent: 0, local: 0 }; renderPA(); };
  function readCfg() {
    cfg.url = $("paUrl").value.trim(); cfg.deviceId = ($("deviceId").value.trim() || "UNIT-01");
    cfg.interval = clamp(parseInt($("paInterval").value, 10) || 5, 1, 600); cfg.csvPayload = $("chkCsvPayload").checked; cfg.mode = $("paMode").value;
    $("devId").textContent = cfg.deviceId; saveCfg(); renderPA();
  }
  ["paUrl","deviceId","paInterval","chkCsvPayload","paMode"].forEach(function (id) { $(id).addEventListener("change", readCfg); });
  function saveCfg() { try { localStorage.setItem("e5cc-sim-v1", JSON.stringify({ cfg: cfg, speed: $("speedSel").value })); } catch (e) {} }
  function loadCfg() {
    try {
      var d = JSON.parse(localStorage.getItem("e5cc-sim-v1") || "null");
      if (d && d.cfg) { cfg = Object.assign(cfg, d.cfg); $("paUrl").value = cfg.url; $("deviceId").value = cfg.deviceId; $("paInterval").value = cfg.interval; $("chkCsvPayload").checked = cfg.csvPayload; $("paMode").value = cfg.mode; }
      if (d && d.speed) $("speedSel").value = d.speed;
    } catch (e) {}
    $("devId").textContent = cfg.deviceId;
  }
  $("speedSel").onchange = saveCfg;

  // ---------- timer ----------
  function readTimer() { T.setSec = clamp(parseInt($("timerMin").value, 10) || 0, 0, 99) * 60 + clamp(parseInt($("timerSec").value, 10) || 0, 0, 59); }
  function updateTimerUI() {
    dTM.set(pad(Math.min(99, Math.floor(T.remaining / 60))) + pad(Math.floor(T.remaining) % 60));
    var pill = $("txtTimer"), map = { idle: ["Idle", "pill"], waiting: ["Waiting for SV band", "pill warn"], soaking: ["Soaking", "pill good"], done: ["Complete", "pill good"] };
    pill.textContent = map[T.state][0]; pill.className = map[T.state][1];
    $("ledSOAK").classList.toggle("on", T.state === "soaking");
  }
  $("btnSetTimer").onclick = function () {
    readTimer(); if (T.state === "idle" || T.state === "done") { T.remaining = T.setSec; T.state = "idle"; }
    ev("timer_set", "Duration set to " + mmss(T.setSec), { durationSec: T.setSec, startMode: $("timerMode").value, bandC: parseFloat($("bandInput").value) });
    updateTimerUI(); banner("Timer set to " + mmss(T.setSec), "ok", 2500);
  };
  ["timerMin","timerSec"].forEach(function (id) { $(id).addEventListener("change", function () { readTimer(); if (!S.run) { T.remaining = T.setSec; T.state = "idle"; updateTimerUI(); } }); });

  // ---------- run control ----------
  function sample() {
    rows.push({ session: S.sessionId, ts: new Date(), t: Math.round(S.elapsed * 10) / 10, pv: r1(S.pv), sv: S.sv, u: r1(S.u), state: S.run ? "RUN" : "STOP", alarm: S.alarm ? 1 : 0, rem: Math.round(T.remaining) });
    if (rows.length > 50000) rows.shift();
    $("pillRows").textContent = "Rows: " + rows.length;
  }
  function startRun() {
    if (S.run) return;
    readTimer(); S.run = true; S.elapsed = 0; plant.ie = 0; plant.dm = 0; plant.pvPrev = plant.T;
    var d = new Date(); S.sessionId = "S-" + fileStamp(d);
    if ($("chkTimer").checked) { T.remaining = T.setSec; T.state = $("timerMode").value === "start" ? "soaking" : "waiting"; } else { T.state = "idle"; T.remaining = T.setSec; }
    $("btnStart").disabled = true; $("btnStop").disabled = false;
    ev("run_start", "RUN started. SV=" + S.sv + " C" + ($("chkTimer").checked ? ", timer " + mmss(T.setSec) + " (" + $("timerMode").selectedOptions[0].text + ")" : ", no timer"),
      { timerEnabled: $("chkTimer").checked, durationSec: T.setSec });
    if (T.state === "soaking") ev("timer_start", "Soak timer started: " + mmss(T.setSec));
    sample(); updateTimerUI(); updateStatusUI(); banner("RUN started (" + S.sessionId + ")", "ok", 3000);
  }
  function stopRun(reason) {
    if (!S.run) return;
    S.run = false; sample();
    $("btnStart").disabled = false; $("btnStop").disabled = true;
    var wasSoak = T.state === "soaking" || T.state === "waiting";
    if (T.state !== "done") { T.state = "idle"; T.remaining = T.setSec; }
    ev("run_stop", "STOP (" + (reason || "operator") + "). PV=" + fmtNum(S.pv) + " C, elapsed " + mmss(S.elapsed), { reason: reason || "operator", elapsedSec: Math.round(S.elapsed), aborted: wasSoak && reason !== "timer_complete" });
    updateTimerUI(); updateStatusUI(); banner("STOP (" + (reason || "operator") + ")", "info", 3000);
  }
  $("btnStart").onclick = startRun;
  $("btnStop").onclick = function () { stopRun("operator"); };
  $("btnCool").onclick = function () { plant.T = parseFloat($("ambInput").value) || 25; plant.ie = 0; plant.dm = 0; plant.pvPrev = plant.T; S.pv = plant.T; refreshDisplays(); banner("Plant reset to ambient.", "info", 2500); };
  function updateStatusUI() {
    $("ledSTOP").classList.toggle("on", !S.run); $("ledRUN").classList.toggle("on", S.run);
    var p = $("pillState"); p.textContent = S.run ? "RUN" : "STOP"; p.className = "pill " + (S.run ? "good" : "");
    $("txtSession").textContent = "Session: " + S.sessionId; $("txtElapsed").textContent = "Elapsed: " + mmss(S.elapsed); $("txtOut").textContent = "Output: " + r1(S.u).toFixed(1) + " %";
  }

  // ---------- export ----------
  var DL = null;
  try { if (window.claude && window.claude.use) window.claude.use("downloads").then(function (d) { DL = d; }, function () {}); } catch (e) {}
  function dl(name, data, type) {
    if (DL) { DL.save({ filename: name, data: data }).catch(function (e) { if (e && e.code === "declined") banner("Save cancelled.", "info", 2500); else banner("Could not save the file here.", "err", 4000); }); return; }
    var a = document.createElement("a"); a.href = URL.createObjectURL(new Blob([data], { type: type })); a.download = name; document.body.appendChild(a); a.click(); a.remove();
    setTimeout(function () { URL.revokeObjectURL(a.href); }, 4000);
  }
  function csvEsc(v) { v = String(v); return /[",\r\n]/.test(v) ? '"' + v.replace(/"/g, '""') + '"' : v; }
  var HEAD = ["Session", "Timestamp", "Elapsed_s", "PV_C", "SV_C", "Output_pct", "State", "Alarm", "TimerRemaining_s"];
  function dataRows() { return rows.map(function (r) { return [r.session, fmtTs(r.ts), r.t, r.pv, r.sv, r.u, r.state, r.alarm, r.rem]; }); }
  function buildCsv() { return "\ufeff" + [HEAD].concat(dataRows()).map(function (r) { return r.map(csvEsc).join(","); }).join("\r\n"); }
  function baseName() { return "E5CC_" + cfg.deviceId + "_" + fileStamp(new Date()); }
  function summaryRows() {
    var pvs = rows.map(function (r) { return r.pv; }), n = pvs.length, last = rows[n - 1];
    var sessions = {}; rows.forEach(function (r) { sessions[r.session] = 1; });
    return [["Item", "Value"], ["Device ID", cfg.deviceId], ["Exported at", fmtTs(new Date())], ["Sessions in file", Object.keys(sessions).length], ["Samples", n],
      ["First sample", fmtTs(rows[0].ts)], ["Last sample", fmtTs(last.ts)], ["PV minimum (C)", Math.min.apply(null, pvs)], ["PV maximum (C)", Math.max.apply(null, pvs)],
      ["PV average (C)", Math.round(pvs.reduce(function (a, b) { return a + b; }, 0) / n * 100) / 100], ["Last SV (C)", last.sv], ["Alarm samples", rows.filter(function (r) { return r.alarm; }).length],
      ["P band (C)", prm.p], ["I (s)", prm.i], ["d (s)", prm.d], ["AL-1 (C)", prm.al1]];
  }
  function doExport(fmt, source) {
    if (!rows.length) { banner("No data yet. Press START to collect samples first.", "err"); return false; }
    var name = baseName() + (fmt === "xlsx" ? ".xlsx" : ".csv"), csv = buildCsv();
    if (fmt === "xlsx") {
      var evRows = [["Timestamp", "Event", "Detail"]].concat(events.map(function (e) { return [fmtTs(e.ts), e.type, e.detail]; }));
      var bytes = buildXlsx([{ name: "Telemetry", rows: [HEAD].concat(dataRows()), widths: [20, 20, 11, 9, 9, 11, 8, 8, 18] }, { name: "Events", rows: evRows, widths: [20, 16, 70] }, { name: "Summary", rows: summaryRows(), widths: [22, 26] }]);
      dl(name, bytes, "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet");
    } else dl(name, csv, "text/csv");
    var extra = { format: fmt, fileName: name, rowCount: rows.length, trigger: source || "manual" };
    if (cfg.csvPayload) extra.csv = csv.replace(/^\ufeff/, "");
    ev("export", fmt.toUpperCase() + " exported: " + name + " (" + rows.length + " rows)", extra);
    banner("Exported " + rows.length + " rows to " + name, "ok");
    return true;
  }
  $("btnExportCsv").onclick = function () { doExport("csv", "button"); };
  $("btnExportXlsx").onclick = function () { doExport("xlsx", "button"); };
  $("btnExportEvents").onclick = function () {
    if (!events.length) { banner("No events to export yet.", "err"); return; }
    var csv = "\ufeff" + [["Timestamp", "Event", "Detail"]].concat(events.map(function (e) { return [fmtTs(e.ts), e.type, e.detail]; })).map(function (r) { return r.map(csvEsc).join(","); }).join("\r\n");
    dl(baseName() + "_events.csv", csv, "text/csv"); banner("Exported " + events.length + " events.", "ok", 3000);
  };
  $("btnClearData").onclick = function () { rows = []; chartBuf = []; events = []; $("pillRows").textContent = "Rows: 0"; renderEvents(); drawChart(); banner("Data and event log cleared.", "info", 2500); };

  // ---------- chart ----------
  function drawChart() {
    var cv = $("chart"), dpr = window.devicePixelRatio || 1, w = cv.clientWidth, h = cv.clientHeight;
    if (!w || !h) return; cv.width = w * dpr; cv.height = h * dpr;
    var c = cv.getContext("2d"); c.setTransform(dpr, 0, 0, dpr, 0, 0); c.clearRect(0, 0, w, h);
    var L = 44, R = 10, Tp = 12, B = 22, pw = w - L - R, ph = h - Tp - B;
    var vals = chartBuf.reduce(function (a, p) { a.push(p.pv, p.sv); return a; }, [S.sv]);
    var lo = Math.min.apply(null, vals.concat([plant.T])), hi = Math.max.apply(null, vals.concat([plant.T]));
    lo = Math.floor((lo - 5) / 10) * 10; hi = Math.ceil((hi + 5) / 10) * 10; if (hi - lo < 40) hi = lo + 40;
    c.font = "11px Segoe UI, Arial"; c.fillStyle = "#93a0ab"; c.strokeStyle = "#252c33"; c.lineWidth = 1;
    for (var i = 0; i <= 4; i++) { var y = Tp + ph * i / 4; c.beginPath(); c.moveTo(L, y); c.lineTo(w - R, y); c.stroke(); c.fillText(Math.round(hi - (hi - lo) * i / 4) + "", 6, y + 4); }
    c.fillText("last " + Math.min(600, chartBuf.length) + " s", L, h - 6);
    function plot(key, color, dash) {
      if (chartBuf.length < 2) return; c.beginPath(); c.strokeStyle = color; c.lineWidth = 2; c.setLineDash(dash || []);
      chartBuf.forEach(function (p, i) { var x = L + pw * i / Math.max(1, 599), y = Tp + ph * (1 - (p[key] - lo) / (hi - lo)); if (i) c.lineTo(x, y); else c.moveTo(x, y); });
      c.stroke(); c.setLineDash([]);
    }
    plot("sv", "#38ff7c", [6, 4]); plot("pv", "#ff5a4f");
    c.fillStyle = "#ff5a4f"; c.fillRect(w - 120, 6, 10, 3); c.fillStyle = "#cfd8df"; c.fillText("PV", w - 105, 11);
    c.fillStyle = "#38ff7c"; c.fillRect(w - 75, 6, 10, 3); c.fillStyle = "#cfd8df"; c.fillText("SV", w - 60, 11);
  }
  window.addEventListener("resize", drawChart);

  // ---------- main loop ----------
  var lastSample = 0, lastSend = 0, tickMs = 200;
  function tick() {
    var speed = parseFloat($("speedSel").value) || 1, dt = tickMs / 1000 * speed, amb = parseFloat($("ambInput").value);
    if (isNaN(amb)) amb = 25;
    simStep(plant, prm, S.sv, S.run, dt, amb);
    var noise = Math.max(0, parseFloat($("noiseInput").value) || 0);
    S.pv = plant.T + (Math.random() + Math.random() + Math.random() - 1.5) * 0.8 * noise * 2; S.u = plant.u;
    var now = Date.now();
    if (S.run) {
      S.elapsed += dt;
      if (T.state === "waiting" && Math.abs(S.pv - S.sv) <= (parseFloat($("bandInput").value) || 2)) { T.state = "soaking"; ev("timer_start", "PV reached SV band. Soak timer started: " + mmss(T.setSec)); }
      if (T.state === "soaking") {
        T.remaining -= dt;
        if (T.remaining <= 0) {
          T.remaining = 0; T.state = "done"; updateTimerUI();
          ev("timer_done", "Soak timer complete at PV=" + fmtNum(S.pv) + " C", { durationSec: T.setSec });
          beep(880, 0.25, 3); banner("Timer complete. Hold time reached.", "ok", 8000);
          if ($("chkAutoExport").checked) doExport("csv", "timer_complete");
          if ($("chkAutoStop").checked) stopRun("timer_complete");
        }
      }
      if (now - lastSample >= 1000) { lastSample = now; sample(); }
      if (now - lastSend >= cfg.interval * 1000) { lastSend = now; sendPA("telemetry", {}); }
    }
    // alarm (absolute upper limit)
    if (!S.alarm && S.pv > prm.al1) { S.alarm = true; ev("alarm", "AL-1 high alarm: PV " + fmtNum(S.pv) + " C > " + prm.al1 + " C", { limit: prm.al1 }); beep(1200, 0.2, 4); banner("ALARM: PV above AL-1 (" + prm.al1 + " C)", "err", 10000); }
    else if (S.alarm && S.pv < prm.al1 - 1) { S.alarm = false; ev("alarm_clear", "AL-1 cleared: PV " + fmtNum(S.pv) + " C"); banner("Alarm cleared.", "ok", 3000); }
    if (now - (tick.lastChart || 0) >= 1000) { tick.lastChart = now; chartBuf.push({ pv: S.pv, sv: S.sv }); if (chartBuf.length > 600) chartBuf.shift(); drawChart(); }
    // displays + LEDs
    if (menuIdx === 0) dPV.set(fmtNum(S.pv)); else if (menuIdx > 0) { /* parameter shown */ }
    $("ledOUT1").classList.toggle("on", S.run && ((now % 1000) / 1000) < S.u / 100);
    $("ledSUB1").classList.toggle("on", S.alarm && (now % 600) < 400);
    if (T.state === "soaking" || T.state === "waiting" || T.state === "idle") { if (T.state === "idle" && !S.run) T.remaining = T.setSec; }
    updateTimerUI(); updateStatusUI();
  }

  // ---------- init ----------
  loadCfg(); readTimer(); T.remaining = T.setSec; syncParamInputs(); renderEvents(); renderPA();
  S.pv = plant.T; refreshDisplays(); updateTimerUI(); updateStatusUI(); drawChart();
  setInterval(tick, tickMs);
})();
</script>
</body>
</html>
