<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#4f46e5">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="apple-mobile-web-app-title" content="家庭庫存">
<title>家庭庫存記錄</title>
<style>
  * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
  html, body { margin: 0; padding: 0; }
  body { background: #f9fafb; font-family: system-ui, -apple-system, "Noto Sans TC", "PingFang TC", "Microsoft JhengHei", sans-serif; color: #111827; }
  button { font-family: inherit; }
  input, select { font-family: inherit; }
  input, select, textarea { font-size: 16px; } /* 避免 iOS 自動放大 */
  .wrap { max-width: 640px; margin: 0 auto; padding: 12px 16px 120px; }
  .topbar { position: sticky; top: 0; z-index: 30; background: rgba(249,250,251,0.92); backdrop-filter: blur(8px); border-bottom: 1px solid #f1f5f9; }
  .topbar-in { max-width: 640px; margin: 0 auto; padding: 12px 16px; display: flex; align-items: center; gap: 10px; }
  h1 { font-size: 19px; font-weight: 700; margin: 0; flex: 1; }
  .iconbtn { background: none; border: none; cursor: pointer; color: #9ca3af; padding: 8px; display: flex; }
  .scrollx { display: flex; gap: 6px; overflow-x: auto; padding-bottom: 2px; -webkit-overflow-scrolling: touch; }
  .card { background: #fff; border-radius: 14px; padding: 14px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); }
  .fab { position: fixed; bottom: 84px; z-index: 40; width: 58px; height: 58px; border-radius: 999px; background: #4f46e5; color: #fff; border: none; box-shadow: 0 6px 18px rgba(79,70,229,0.45); cursor: pointer; display: flex; align-items: center; justify-content: center; right: max(20px, calc((100vw - 640px)/2 + 20px)); }
  .nav { position: fixed; bottom: 0; left: 0; right: 0; z-index: 35; background: #fff; border-top: 1px solid #f1f5f9; box-shadow: 0 -2px 12px rgba(0,0,0,0.04); }
  .nav-in { max-width: 640px; margin: 0 auto; display: flex; padding: 8px 8px calc(8px + env(safe-area-inset-bottom)); }
  .navbtn { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; padding: 8px; background: none; border: none; cursor: pointer; }
  .navbtn span { font-size: 11px; font-weight: 600; }
  .dot { position: absolute; top: -6px; right: -10px; min-width: 16px; height: 16px; padding: 0 4px; border-radius: 999px; background: #ef4444; color: #fff; font-size: 10px; font-weight: 700; display: flex; align-items: center; justify-content: center; }
  .overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.4); z-index: 50; display: flex; align-items: flex-end; justify-content: center; }
  .sheet { width: 100%; max-width: 640px; background: #fff; border-radius: 20px 20px 0 0; max-height: 88vh; display: flex; flex-direction: column; box-shadow: 0 -4px 24px rgba(0,0,0,0.15); }
  .sheet-h { display: flex; align-items: center; justify-content: space-between; padding: 14px 18px; border-bottom: 1px solid #f1f5f9; flex-shrink: 0; }
  .sheet-h span { font-size: 17px; font-weight: 700; }
  .sheet-b { overflow-y: auto; padding: 18px; -webkit-overflow-scrolling: touch; }
  .closebtn { background: #f3f4f6; border: none; border-radius: 999px; width: 34px; height: 34px; display: flex; align-items: center; justify-content: center; cursor: pointer; color: #6b7280; }
  .label { font-size: 13px; color: #6b7280; font-weight: 600; margin-bottom: 8px; }
  .txt { width: 100%; padding: 14px; border-radius: 12px; border: 1.5px solid #e5e7eb; outline: none; }
  .txt:focus { border-color: #4f46e5; }
  .stepper { display: flex; align-items: center; border: 1.5px solid #e5e7eb; border-radius: 10px; width: fit-content; }
  .step { display: flex; align-items: center; justify-content: center; width: 40px; height: 40px; background: none; border: none; cursor: pointer; color: #6b7280; }
  .stepval { min-width: 40px; text-align: center; font-size: 16px; font-weight: 700; }
  .outline { padding: 9px 13px; border-radius: 10px; font-size: 14px; font-weight: 600; cursor: pointer; border: 1.5px solid #e5e7eb; background: #fff; color: #374151; }
  .date { padding: 9px 10px; border-radius: 10px; border: 1.5px solid #e5e7eb; color: #374151; }
  .mini { display: flex; align-items: center; gap: 4px; padding: 8px 12px; border-radius: 999px; font-size: 13px; font-weight: 600; cursor: pointer; border: 1px solid #e5e7eb; background: #f9fafb; color: #6b7280; }
  .mini.hot { border-color: #fbbf24; background: #fef3c7; color: #d97706; }
  .empty { text-align: center; padding: 60px 0; color: #9ca3af; }
  svg { display: block; }
  .row { display: flex; align-items: center; }
</style>
</head>
<body>
<div id="app"></div>

<script>
// ================= 資料模型 =================
const CATEGORIES = [
  { id:"food", label:"食品", color:"#f59e0b" },
  { id:"daily", label:"日用品", color:"#3b82f6" },
  { id:"clean", label:"清潔", color:"#10b981" },
  { id:"medicine", label:"藥品", color:"#ef4444" },
  { id:"kitchen", label:"廚房", color:"#8b5cf6" },
  { id:"other", label:"其他", color:"#6b7280" },
];
const catOf = id => CATEGORIES.find(c => c.id === id) || CATEGORIES[5];
const DEFAULT_LOCATIONS = ["冰箱","廚房","浴室","床底","客廳","衣櫥","其他"];
const DEFAULT_CATLOC = { food:"冰箱", daily:"客廳", clean:"浴室", medicine:"客廳", kitchen:"廚房", other:"其他" };
const QUICK_DATES = [ {label:"+1週",days:7},{label:"+1月",days:30},{label:"+3月",days:90},{label:"+6月",days:180},{label:"+1年",days:365} ];

// ================= 圖示 (inline SVG) =================
const I = {
  pkg:'<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m7.5 4.27 9 5.15"/><path d="M21 8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16Z"/><path d="m3.3 7 8.7 5 8.7-5"/><path d="M12 22V12"/></svg>',
  cart:'<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="8" cy="21" r="1"/><circle cx="19" cy="21" r="1"/><path d="M2.05 2.05h2l2.66 12.42a2 2 0 0 0 2 1.58h9.78a2 2 0 0 0 1.95-1.57l1.65-7.43H5.12"/></svg>',
  plus:'<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M12 5v14"/></svg>',
  minusS:'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M5 12h14"/></svg>',
  plusS:'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M5 12h14M12 5v14"/></svg>',
  x:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M18 6 6 18M6 6l12 12"/></svg>',
  trash:'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 6h18M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/></svg>',
  cal:'<svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18"/></svg>',
  pin:'<svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>',
  open:'<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.91 8.84 8.56 2.23a1.93 1.93 0 0 0-1.81 0L3.1 4.13a2.12 2.12 0 0 0-.05 3.69l12.22 6.93a2 2 0 0 0 1.94 0L21 12.51a2.12 2.12 0 0 0-.09-3.67Z"/><path d="m3.09 8.84 12.35-6.61M20.91 8.84 8.56 2.23"/><path d="M3.05 7.82v8.66a2 2 0 0 0 1.11 1.79l6.5 3.48a2 2 0 0 0 1.9 0l6.5-3.48a2 2 0 0 0 1.09-1.79V7.82"/><path d="M12 22.76V11"/></svg>',
  check:'<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>',
  gear:'<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12.22 2h-.44a2 2 0 0 0-2 2v.18a2 2 0 0 1-1 1.73l-.43.25a2 2 0 0 1-2 0l-.15-.08a2 2 0 0 0-2.73.73l-.22.38a2 2 0 0 0 .73 2.73l.15.1a2 2 0 0 1 1 1.72v.51a2 2 0 0 1-1 1.74l-.15.09a2 2 0 0 0-.73 2.73l.22.38a2 2 0 0 0 2.73.73l.15-.08a2 2 0 0 1 2 0l.43.25a2 2 0 0 1 1 1.73V20a2 2 0 0 0 2 2h.44a2 2 0 0 0 2-2v-.18a2 2 0 0 1 1-1.73l.43-.25a2 2 0 0 1 2 0l.15.08a2 2 0 0 0 2.73-.73l.22-.39a2 2 0 0 0-.73-2.73l-.15-.08a2 2 0 0 1-1-1.74v-.5a2 2 0 0 1 1-1.74l.15-.09a2 2 0 0 0 .73-2.73l-.22-.38a2 2 0 0 0-2.73-.73l-.15.08a2 2 0 0 1-2 0l-.43-.25a2 2 0 0 1-1-1.73V4a2 2 0 0 0-2-2Z"/><circle cx="12" cy="12" r="3"/></svg>',
  arrow:'<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><path d="M8 12h8M12 8l4 4-4 4"/></svg>',
  alert:'<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m21.73 18-8-14a2 2 0 0 0-3.48 0l-8 14A2 2 0 0 0 4 21h16a2 2 0 0 0 1.73-3Z"/><path d="M12 9v4M12 17h.01"/></svg>',
  search:'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.3-4.3"/></svg>',
};

// ================= 狀態 =================
const emptyForm = () => ({ name:"", cat:"food", qty:1, location:DEFAULT_CATLOC.food, locTouched:false, catTouched:false, threshold:1, expiry:"", opened:"", openDays:"" });
let S = {
  tab:"stock", sheet:null,
  items:[], shopping:[], locations:[...DEFAULT_LOCATIONS], catloc:{...DEFAULT_CATLOC}, catmemory:{},
  form: emptyForm(),
  search:"", filterCat:"all",
  buyName:"",
  convertId:null, cv:{cat:"food",qty:1,expiry:""},
  newLoc:"",
};

// ================= 儲存 =================
const K = { items:"inv_items", shopping:"inv_shopping", locations:"inv_locations", catloc:"inv_catloc", catmemory:"inv_catmemory" };
function load() {
  try { const v = localStorage.getItem(K.items); if (v) S.items = JSON.parse(v); } catch(e){}
  try { const v = localStorage.getItem(K.shopping); if (v) S.shopping = JSON.parse(v); } catch(e){}
  try { const v = localStorage.getItem(K.locations); if (v) S.locations = JSON.parse(v); } catch(e){}
  try { const v = localStorage.getItem(K.catloc); if (v) S.catloc = JSON.parse(v); } catch(e){}
  try { const v = localStorage.getItem(K.catmemory); if (v) S.catmemory = JSON.parse(v); } catch(e){}
}
function save() {
  try {
    localStorage.setItem(K.items, JSON.stringify(S.items));
    localStorage.setItem(K.shopping, JSON.stringify(S.shopping));
    localStorage.setItem(K.locations, JSON.stringify(S.locations));
    localStorage.setItem(K.catloc, JSON.stringify(S.catloc));
    localStorage.setItem(K.catmemory, JSON.stringify(S.catmemory));
  } catch(e){}
}

// ================= 工具 =================
const esc = s => String(s).replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;").replace(/"/g,"&quot;").replace(/'/g,"&#39;");
const uid = () => Date.now()+""+Math.random().toString(36).slice(2,6);
const todayStr = () => new Date().toISOString().slice(0,10);
const addDaysFrom = (base,days) => { const d = new Date(base+"T00:00:00"); d.setDate(d.getDate()+days); return d.toISOString().slice(0,10); };
const addDays = days => addDaysFrom(todayStr(),days);
const daysLeft = s => { if(!s) return null; const d=new Date(s+"T00:00:00"), n=new Date(todayStr()+"T00:00:00"); return Math.round((d-n)/86400000); };
function effectiveExpiry(it){ const a=[]; if(it.expiry) a.push(it.expiry); if(it.opened&&it.openDays) a.push(addDaysFrom(it.opened,Number(it.openDays))); return a.length? a.sort()[0]:null; }
function statusOf(dl){
  if(dl===null) return {color:"#9ca3af",bg:"#f3f4f6",text:"無效期"};
  if(dl<0) return {color:"#dc2626",bg:"#fee2e2",text:"過期 "+(-dl)+" 天"};
  if(dl<=7) return {color:"#dc2626",bg:"#fee2e2",text:"剩 "+dl+" 天"};
  if(dl<=30) return {color:"#d97706",bg:"#fef3c7",text:"剩 "+dl+" 天"};
  return {color:"#059669",bg:"#d1fae5",text:"剩 "+dl+" 天"};
}
const isLow = i => i.qty <= (i.threshold ?? 0);

// ================= HTML 片段 =================
function pill(active,color,label,onclick){
  const st = active
    ? "background:"+color+";color:#fff;border:1.5px solid "+color+";"
    : "background:#fff;color:#6b7280;border:1.5px solid #e5e7eb;";
  return '<button onclick="'+onclick+'" style="padding:10px 16px;border-radius:999px;font-size:14px;font-weight:600;cursor:pointer;white-space:nowrap;'+st+'">'+esc(label)+'</button>';
}
function chip(active,color,label,onclick){
  const st = active
    ? "background:"+color+";color:#fff;border:1.5px solid "+color+";"
    : "background:#fff;color:#6b7280;border:1.5px solid #e5e7eb;";
  return '<button onclick="'+onclick+'" style="flex-shrink:0;padding:8px 15px;border-radius:999px;font-size:14px;font-weight:600;cursor:pointer;white-space:nowrap;'+st+'">'+esc(label)+'</button>';
}

function itemCard(item){
  const eff = effectiveExpiry(item);
  const st = statusOf(daysLeft(eff));
  const c = catOf(item.cat);
  const low = isLow(item);
  const openLimited = item.opened && item.openDays && (!item.expiry || addDaysFrom(item.opened,Number(item.openDays)) <= item.expiry);
  let tags = '<span style="font-size:16px;font-weight:600;">'+esc(item.name)+'</span>';
  tags += '<span style="font-size:11px;font-weight:600;color:'+c.color+';background:'+c.color+'18;padding:2px 8px;border-radius:999px;">'+c.label+'</span>';
  if(item.location) tags += '<span style="font-size:11px;color:#0891b2;background:#cffafe;padding:2px 8px;border-radius:999px;display:flex;align-items:center;gap:2px;">'+I.pin+esc(item.location)+'</span>';
  if(low) tags += '<span style="font-size:11px;font-weight:700;color:#d97706;background:#fef3c7;padding:2px 8px;border-radius:999px;">需補貨</span>';
  let meta = '<span style="font-size:12px;font-weight:600;color:'+st.color+';background:'+st.bg+';padding:3px 9px;border-radius:6px;">'+st.text+'</span>';
  if(eff) meta += '<span style="font-size:11px;color:#9ca3af;display:flex;align-items:center;gap:2px;">'+I.cal+' '+eff+(openLimited?'（開封）':'')+'</span>';
  if(item.opened) meta += '<span style="font-size:11px;color:#d97706;display:flex;align-items:center;gap:2px;">'+I.open+esc(item.opened)+' 開</span>';
  const qbox = 'border:1.5px solid '+(low?'#fbbf24':'#e5e7eb')+';border-radius:10px;background:'+(low?'#fffbeb':'#fff')+';';
  const qcol = low?'#d97706':'#111827';
  let actions = '';
  if(!item.opened) actions += '<button class="mini" onclick="markOpened(\''+item.id+'\')">'+I.open+' 開封</button>';
  actions += '<button class="mini '+(low?'hot':'')+'" onclick="addBuyFromItem(\''+item.id+'\')">'+I.cart+' 待買</button>';
  return '<div class="card" style="border-left:4px solid '+c.color+';">'
    + '<div style="display:flex;align-items:flex-start;gap:10px;">'
      + '<div style="flex:1;min-width:0;">'
        + '<div style="display:flex;align-items:center;gap:6px;margin-bottom:6px;flex-wrap:wrap;">'+tags+'</div>'
        + '<div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap;">'+meta+'</div>'
      + '</div>'
      + '<button onclick="removeItem(\''+item.id+'\')" style="background:none;border:none;cursor:pointer;color:#d1d5db;display:flex;padding:6px;">'+I.trash+'</button>'
    + '</div>'
    + '<div style="display:flex;align-items:center;gap:8px;margin-top:12px;">'
      + '<div class="row" style="'+qbox+'">'
        + '<button class="step" onclick="updateQty(\''+item.id+'\',-1)">'+I.minusS+'</button>'
        + '<span class="stepval" style="color:'+qcol+';">'+item.qty+'</span>'
        + '<button class="step" onclick="updateQty(\''+item.id+'\',1)">'+I.plusS+'</button>'
      + '</div>'
      + '<div style="flex:1;"></div>' + actions
    + '</div>'
  + '</div>';
}

function filteredItems(){
  let list = S.items.filter(i => {
    if(S.filterCat!=="all" && i.cat!==S.filterCat) return false;
    if(S.search && !i.name.toLowerCase().includes(S.search.toLowerCase())) return false;
    return true;
  });
  list.sort((a,b)=>{ const ea=effectiveExpiry(a),eb=effectiveExpiry(b); if(!ea&&!eb)return 0; if(!ea)return 1; if(!eb)return -1; return ea.localeCompare(eb); });
  return list;
}

function stockListHTML(){
  const list = filteredItems();
  if(list.length===0){
    const msg = S.items.length===0 ? "還沒有任何項目，點右下角 ＋ 新增" : "沒有符合的項目";
    return '<div class="empty">'+I.pkg+'<p style="font-size:14px;">'+msg+'</p></div>';
  }
  return '<div style="display:flex;flex-direction:column;gap:10px;">'+list.map(itemCard).join("")+'</div>';
}

function stockView(){
  const expiringSoon = S.items.filter(i=>{const dl=daysLeft(effectiveExpiry(i));return dl!==null&&dl<=7;}).length;
  const lowCount = S.items.filter(isLow).length;
  let alerts = '';
  if(expiringSoon>0||lowCount>0){
    alerts = '<div style="display:flex;gap:8px;margin-bottom:12px;flex-wrap:wrap;">';
    if(expiringSoon>0) alerts += '<div style="flex:1;min-width:130px;background:#fee2e2;border-radius:10px;padding:10px 12px;display:flex;align-items:center;gap:6px;color:#dc2626;">'+I.alert+'<span style="font-size:13px;font-weight:700;">'+expiringSoon+' 項即將到期</span></div>';
    if(lowCount>0) alerts += '<div style="flex:1;min-width:130px;background:#fef3c7;border-radius:10px;padding:10px 12px;display:flex;align-items:center;gap:6px;color:#d97706;">'+I.cart+'<span style="font-size:13px;font-weight:700;">'+lowCount+' 項需補貨</span></div>';
    alerts += '</div>';
  }
  const chips = '<div class="scrollx" style="margin-bottom:14px;">'
    + chip(S.filterCat==="all","#4f46e5","全部","setFilter('all')")
    + CATEGORIES.map(c=>chip(S.filterCat===c.id,c.color,c.label,"setFilter('"+c.id+"')")).join("")
    + '</div>';
  const searchBox = '<div style="position:relative;margin-bottom:10px;">'
    + '<span style="position:absolute;left:12px;top:13px;color:#9ca3af;">'+I.search+'</span>'
    + '<input id="q" class="txt" style="padding-left:38px;" placeholder="搜尋品名…" value="'+esc(S.search)+'" oninput="onSearch(this.value)">'
    + '</div>';
  return alerts + searchBox + chips + '<div id="stockList">'+stockListHTML()+'</div>';
}

function shopView(){
  if(S.shopping.length===0){
    return '<div class="empty">'+I.cart+'<p style="font-size:14px;">待買清單是空的，點右下角 ＋ 新增</p></div>';
  }
  const sorted = [...S.shopping].sort((a,b)=>a.done-b.done);
  let rows = sorted.map(s=>{
    const dim = (s.done && S.convertId!==s.id) ? "opacity:0.55;" : "";
    let convertBtn = '';
    if(s.done && S.convertId!==s.id) convertBtn = '<button onclick="openConvert(\''+s.id+'\')" style="display:flex;align-items:center;gap:4px;padding:8px 12px;border-radius:10px;font-size:13px;font-weight:600;cursor:pointer;border:none;background:#4f46e5;color:#fff;">'+I.arrow+' 轉入</button>';
    let panel = '';
    if(S.convertId===s.id){
      const cats = CATEGORIES.map(c=>pill(S.cv.cat===c.id,c.color,c.label,"setCv('cat','"+c.id+"')")).join("");
      const presets = QUICK_DATES.map(q=>'<button class="outline" onclick="setCv(\'expiry\',\''+addDays(q.days)+'\')">'+q.label+'</button>').join("");
      panel = '<div style="padding:0 14px 14px;border-top:1px solid #f3f4f6;padding-top:12px;">'
        + '<div style="font-size:12px;color:#6b7280;font-weight:600;margin-bottom:8px;">分類（位置自動帶入）</div>'
        + '<div style="display:flex;flex-wrap:wrap;gap:6px;margin-bottom:12px;">'+cats+'</div>'
        + '<div style="display:flex;align-items:center;gap:12px;flex-wrap:wrap;margin-bottom:12px;">'
          + '<div class="row" style="gap:8px;"><span style="font-size:13px;color:#6b7280;font-weight:600;">數量</span>'
            + '<div class="stepper"><button class="step" onclick="setCvQty(-1)">'+I.minusS+'</button><span class="stepval" style="min-width:34px;font-size:15px;">'+S.cv.qty+'</span><button class="step" onclick="setCvQty(1)">'+I.plusS+'</button></div></div>'
          + '<input type="date" class="date" value="'+S.cv.expiry+'" onchange="setCv(\'expiry\',this.value)">'
        + '</div>'
        + '<div style="display:flex;gap:6px;flex-wrap:wrap;margin-bottom:12px;">'+presets+'</div>'
        + '<div style="display:flex;gap:8px;">'
          + '<button onclick="doConvert(\''+s.id+'\')" style="flex:1;padding:12px;background:#4f46e5;color:#fff;border:none;border-radius:10px;font-size:15px;font-weight:600;cursor:pointer;">確認轉入</button>'
          + '<button onclick="cancelConvert()" style="padding:12px 16px;background:#fff;border:1.5px solid #e5e7eb;border-radius:10px;font-size:15px;font-weight:600;color:#6b7280;cursor:pointer;">取消</button>'
        + '</div>'
      + '</div>';
    }
    const box = 'width:28px;height:28px;border-radius:8px;border:2px solid '+(s.done?'#10b981':'#d1d5db')+';background:'+(s.done?'#10b981':'#fff')+';cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;';
    return '<div class="card" style="padding:0;'+dim+'">'
      + '<div style="padding:14px;display:flex;align-items:center;gap:12px;">'
        + '<button onclick="toggleBuy(\''+s.id+'\')" style="'+box+'">'+(s.done?I.check:'')+'</button>'
        + '<span style="flex:1;font-size:16px;font-weight:500;'+(s.done?'text-decoration:line-through;':'')+'">'+esc(s.name)+'</span>'
        + convertBtn
        + '<button onclick="removeBuy(\''+s.id+'\')" style="background:none;border:none;cursor:pointer;color:#d1d5db;display:flex;padding:6px;">'+I.trash+'</button>'
      + '</div>' + panel
    + '</div>';
  }).join("");
  let clearBtn = '';
  if(S.shopping.some(s=>s.done)) clearBtn = '<button onclick="clearDone()" style="margin-top:14px;padding:10px 16px;background:#fff;border:1.5px solid #e5e7eb;border-radius:12px;font-size:14px;font-weight:600;color:#6b7280;cursor:pointer;width:100%;">清除已完成</button>';
  return '<div style="display:flex;flex-direction:column;gap:10px;">'+rows+'</div>'+clearBtn;
}

function stepperHTML(label, dec, val, inc){
  return '<div><div class="label">'+label+'</div><div class="stepper">'
    + '<button class="step" onclick="'+dec+'">'+I.minusS+'</button>'
    + '<span class="stepval">'+val+'</span>'
    + '<button class="step" onclick="'+inc+'">'+I.plusS+'</button></div></div>';
}

function stockSheet(){
  const f = S.form;
  const cats = CATEGORIES.map(c=>pill(f.cat===c.id,c.color,c.label,"pickCat('"+c.id+"')")).join("");
  const locs = S.locations.map(l=>pill(f.location===l,"#0891b2",l,"pickLoc('"+esc(l).replace(/'/g,"\\'")+"')")).join("");
  const presets = QUICK_DATES.map(q=>'<button class="outline" onclick="setForm(\'expiry\',\''+addDays(q.days)+'\')">'+q.label+'</button>').join("");
  let openExtra = '';
  if(f.opened){
    openExtra = '<span style="display:flex;align-items:center;gap:4px;font-size:14px;color:#374151;">後可放 '
      + '<input type="number" min="1" value="'+esc(f.openDays)+'" oninput="setFormRaw(\'openDays\',this.value)" placeholder="天" style="width:60px;padding:10px 8px;border-radius:10px;border:1.5px solid #e5e7eb;"> 天</span>'
      + '<button onclick="clearOpened()" style="background:none;border:none;cursor:pointer;color:#9ca3af;display:flex;">'+I.x+'</button>';
  }
  const clearExp = f.expiry ? '<button onclick="setForm(\'expiry\',\'\')" style="background:none;border:none;cursor:pointer;color:#9ca3af;display:flex;">'+I.x+'</button>' : '';
  const expLabel = '效期'+(f.expiry?' <span style="color:#4f46e5;">（'+f.expiry+'）</span>':'');
  return '<input id="nm" class="txt" style="margin-bottom:14px;" placeholder="輸入品名…" value="'+esc(f.name)+'" oninput="setFormRaw(\'name\',this.value)" onchange="onNameBlur(this.value)">'
    + '<div class="label">分類</div><div style="display:flex;flex-wrap:wrap;gap:8px;margin-bottom:14px;">'+cats+'</div>'
    + '<div class="label">'+I.pin+' 位置</div><div style="display:flex;flex-wrap:wrap;gap:8px;margin-bottom:14px;">'+locs+'</div>'
    + '<div style="display:flex;gap:20px;margin-bottom:14px;flex-wrap:wrap;">'
      + stepperHTML("數量","setFormQty(-1)",f.qty,"setFormQty(1)")
      + stepperHTML("低於補貨","setFormTh(-1)",f.threshold,"setFormTh(1)")
    + '</div>'
    + '<div class="label">'+expLabel+'</div>'
    + '<div style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin-bottom:14px;">'+presets
      + '<input type="date" class="date" value="'+f.expiry+'" onchange="setForm(\'expiry\',this.value)">'+clearExp+'</div>'
    + '<div class="label">'+I.open+' 開封（選填）</div>'
    + '<div style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin-bottom:20px;">'
      + '<button class="outline" onclick="setForm(\'opened\',\''+todayStr()+'\')">今天開封</button>'
      + '<input type="date" class="date" value="'+f.opened+'" onchange="setForm(\'opened\',this.value)">'+openExtra+'</div>'
    + '<div style="display:flex;gap:8px;">'
      + '<button onclick="addItem(true)" style="flex:1;padding:14px;background:#eef2ff;color:#4f46e5;border:none;border-radius:12px;font-size:15px;font-weight:700;cursor:pointer;">新增並繼續</button>'
      + '<button onclick="addItem(false)" style="flex:1;padding:14px;background:#4f46e5;color:#fff;border:none;border-radius:12px;font-size:15px;font-weight:700;cursor:pointer;">新增並關閉</button>'
    + '</div>';
}

function shopSheet(){
  return '<div style="display:flex;gap:8px;">'
    + '<input id="bn" class="txt" placeholder="要買什麼？按 Enter 連續新增…" value="'+esc(S.buyName)+'" oninput="setBuyName(this.value)" onkeydown="if(event.key===\'Enter\')addBuy()">'
    + '<button onclick="addBuy()" style="padding:0 18px;background:#4f46e5;color:#fff;border:none;border-radius:12px;font-size:15px;font-weight:600;cursor:pointer;">新增</button>'
    + '</div><p style="font-size:12px;color:#9ca3af;margin-top:12px;">可連續輸入多筆，完成後關閉即可。</p>';
}

function manageSheet(){
  const locChips = S.locations.map(l=>'<span style="display:flex;align-items:center;gap:4px;padding:8px 8px 8px 14px;border-radius:999px;font-size:14px;font-weight:600;background:#cffafe;color:#0891b2;">'+esc(l)+'<button onclick="removeLocation(\''+esc(l).replace(/'/g,"\\'")+'\')" style="background:none;border:none;cursor:pointer;color:#0891b2;display:flex;padding:0;">'+I.x+'</button></span>').join("");
  const defaults = CATEGORIES.map(c=>{
    const opts = S.locations.map(l=>'<option value="'+esc(l)+'"'+(S.catloc[c.id]===l?' selected':'')+'>'+esc(l)+'</option>').join("");
    return '<div style="display:flex;align-items:center;gap:10px;"><span style="font-size:14px;font-weight:600;color:'+c.color+';width:60px;">'+c.label+'</span>'
      + '<select onchange="setCatDefault(\''+c.id+'\',this.value)" style="flex:1;padding:10px 12px;border-radius:10px;border:1.5px solid #e5e7eb;color:#374151;background:#fff;">'+opts+'</select></div>';
  }).join("");
  return '<div style="display:flex;flex-wrap:wrap;gap:8px;margin-bottom:12px;">'+locChips+'</div>'
    + '<div style="display:flex;gap:8px;margin-bottom:22px;">'
      + '<input id="nl" class="txt" placeholder="新增位置…" value="'+esc(S.newLoc)+'" oninput="setNewLoc(this.value)" onkeydown="if(event.key===\'Enter\')addLocation()">'
      + '<button onclick="addLocation()" style="padding:0 16px;background:#0891b2;color:#fff;border:none;border-radius:12px;font-size:15px;font-weight:600;cursor:pointer;">新增</button>'
    + '</div>'
    + '<div style="font-size:14px;font-weight:700;color:#374151;margin-bottom:10px;">各分類預設位置</div>'
    + '<div style="display:flex;flex-direction:column;gap:8px;">'+defaults+'</div>';
}

function sheetHTML(){
  let title='', body='';
  if(S.sheet==="stock"){ title="新增庫存"; body=stockSheet(); }
  else if(S.sheet==="shop"){ title="新增待買"; body=shopSheet(); }
  else if(S.sheet==="manage"){ title="管理位置"; body=manageSheet(); }
  return '<div class="overlay" onclick="closeSheet(event)">'
    + '<div class="sheet" onclick="event.stopPropagation()">'
      + '<div class="sheet-h"><span>'+title+'</span><button class="closebtn" onclick="closeSheet()">'+I.x+'</button></div>'
      + '<div class="sheet-b">'+body+'</div>'
    + '</div></div>';
}

// ================= 主渲染 =================
function render(){
  const buyCount = S.shopping.filter(s=>!s.done).length;
  const activeColor = "#4f46e5", idle = "#9ca3af";
  const nav = '<div class="nav"><div class="nav-in">'
    + '<button class="navbtn" style="color:'+(S.tab==="stock"?activeColor:idle)+';" onclick="setTab(\'stock\')">'
      + '<div style="position:relative;">'+I.pkg+(S.items.length>0?'<span class="dot">'+S.items.length+'</span>':'')+'</div><span>庫存</span></button>'
    + '<button class="navbtn" style="color:'+(S.tab==="shopping"?activeColor:idle)+';" onclick="setTab(\'shopping\')">'
      + '<div style="position:relative;">'+I.cart+(buyCount>0?'<span class="dot">'+buyCount+'</span>':'')+'</div><span>待買</span></button>'
    + '</div></div>';
  const fab = '<button class="fab" onclick="openAdd()">'+I.plus+'</button>';
  const top = '<div class="topbar"><div class="topbar-in"><span style="color:#4f46e5;display:flex;">'+I.pkg+'</span><h1>家庭庫存記錄</h1><button class="iconbtn" onclick="openSheet(\'manage\')">'+I.gear+'</button></div></div>';
  const content = '<div class="wrap">'+(S.tab==="stock"?stockView():shopView())+'</div>';
  document.getElementById("app").innerHTML = top + content + fab + nav + (S.sheet?sheetHTML():"");
}
// 只更新庫存清單（維持搜尋框焦點）
function renderStockList(){
  const el = document.getElementById("stockList");
  if(el) el.innerHTML = stockListHTML();
}

// ================= 動作 =================
function setTab(t){ S.tab=t; S.convertId=null; render(); }
function setFilter(f){ S.filterCat=f; render(); }
function onSearch(v){ S.search=v; renderStockList(); }

function openAdd(){ openSheet(S.tab==="stock"?"stock":"shop"); }
function openSheet(name){
  S.sheet=name;
  if(name==="stock"){ S.form=emptyForm(); S.form.location = S.locations.includes(S.catloc.food)?S.catloc.food:(S.locations[0]||"其他"); }
  render();
  if(name==="stock") setTimeout(()=>document.getElementById("nm") && document.getElementById("nm").focus(),80);
  if(name==="shop") setTimeout(()=>document.getElementById("bn") && document.getElementById("bn").focus(),80);
}
function closeSheet(ev){ if(ev && ev.type==="click" && ev.target && !ev.target.classList.contains("overlay")) return; S.sheet=null; S.convertId=null; render(); }

// --- 新增庫存表單 ---
function setFormRaw(k,v){ S.form[k]=v; } // 純文字，不重繪（保留輸入焦點）
function setForm(k,v){ S.form[k]=v; render(); }
function setFormQty(d){ S.form.qty=Math.max(1,S.form.qty+d); render(); }
function setFormTh(d){ S.form.threshold=Math.max(0,Number(S.form.threshold)+d); render(); }
function clearOpened(){ S.form.opened=""; S.form.openDays=""; render(); }
function pickCat(id){
  S.form.cat=id; S.form.catTouched=true;
  if(!S.form.locTouched){ const def=S.catloc[id]; S.form.location = S.locations.includes(def)?def:(S.locations[0]||"其他"); }
  render();
}
function pickLoc(l){ S.form.location=l; S.form.locTouched=true; render(); }
function onNameBlur(v){
  S.form.name=v;
  const remembered = S.catmemory[v.trim()];
  if(remembered && !S.form.catTouched){
    S.form.cat=remembered;
    if(!S.form.locTouched){ const def=S.catloc[remembered]; S.form.location = S.locations.includes(def)?def:(S.locations[0]||"其他"); }
    render();
  }
}
function rememberCat(n,c){ const k=n.trim(); if(k){ S.catmemory[k]=c; } }
function addItem(keepOpen){
  const nm = (document.getElementById("nm") ? document.getElementById("nm").value : S.form.name).trim();
  if(!nm){ const el=document.getElementById("nm"); if(el) el.focus(); return; }
  S.form.name=nm;
  rememberCat(nm,S.form.cat);
  S.items.unshift({ id:uid(), name:nm, cat:S.form.cat, qty:S.form.qty, location:S.form.location, threshold:Number(S.form.threshold)||0, expiry:S.form.expiry, opened:S.form.opened, openDays:S.form.openDays, created:todayStr() });
  save();
  const keepCat=S.form.cat;
  S.form=emptyForm(); S.form.cat=keepCat;
  S.form.location = S.locations.includes(S.catloc[keepCat])?S.catloc[keepCat]:(S.locations[0]||"其他");
  if(!keepOpen) S.sheet=null;
  render();
  if(keepOpen) setTimeout(()=>document.getElementById("nm") && document.getElementById("nm").focus(),50);
}
function removeItem(id){ S.items=S.items.filter(i=>i.id!==id); save(); render(); }
function updateQty(id,d){ S.items=S.items.map(i=>i.id===id?{...i,qty:Math.max(0,i.qty+d)}:i); save(); if(S.tab==="stock"&&!S.sheet) renderStockList(); else render(); }
function markOpened(id){ S.items=S.items.map(i=>i.id===id?{...i,opened:todayStr()}:i); save(); renderStockList(); }

// --- 待買 ---
function setBuyName(v){ S.buyName=v; }
function addBuyRaw(n){ const name=n.trim(); if(!name) return; if(!S.shopping.some(s=>s.name===name&&!s.done)) S.shopping.unshift({id:uid(),name,done:false}); save(); }
function addBuy(){ const v=document.getElementById("bn")?document.getElementById("bn").value:S.buyName; addBuyRaw(v); S.buyName=""; render(); setTimeout(()=>document.getElementById("bn")&&document.getElementById("bn").focus(),50); }
function addBuyFromItem(id){ const it=S.items.find(i=>i.id===id); if(it){ addBuyRaw(it.name); render(); } }
function toggleBuy(id){ S.shopping=S.shopping.map(s=>s.id===id?{...s,done:!s.done}:s); save(); render(); }
function removeBuy(id){ S.shopping=S.shopping.filter(s=>s.id!==id); if(S.convertId===id)S.convertId=null; save(); render(); }
function clearDone(){ S.shopping=S.shopping.filter(s=>!s.done); save(); render(); }

// --- 轉入庫存 ---
function openConvert(id){ const s=S.shopping.find(x=>x.id===id); S.convertId=id; S.cv={cat:(s&&S.catmemory[s.name.trim()])||"food",qty:1,expiry:""}; render(); }
function cancelConvert(){ S.convertId=null; render(); }
function setCv(k,v){ S.cv[k]=v; render(); }
function setCvQty(d){ S.cv.qty=Math.max(1,S.cv.qty+d); render(); }
function doConvert(id){
  const s=S.shopping.find(x=>x.id===id); if(!s) return;
  rememberCat(s.name,S.cv.cat);
  const loc = S.locations.includes(S.catloc[S.cv.cat])?S.catloc[S.cv.cat]:(S.locations[0]||"其他");
  S.items.unshift({ id:uid(), name:s.name, cat:S.cv.cat, qty:S.cv.qty, location:loc, threshold:1, expiry:S.cv.expiry, opened:"", openDays:"", created:todayStr() });
  S.shopping=S.shopping.filter(x=>x.id!==id);
  S.convertId=null; S.tab="stock"; save(); render();
}

// --- 位置管理 ---
function setNewLoc(v){ S.newLoc=v; }
function addLocation(){ const el=document.getElementById("nl"); const l=(el?el.value:S.newLoc).trim(); if(l&&!S.locations.includes(l)) S.locations.push(l); S.newLoc=""; save(); render(); }
function removeLocation(l){ S.locations=S.locations.filter(x=>x!==l); Object.keys(S.catloc).forEach(k=>{ if(S.catloc[k]===l) S.catloc[k]="其他"; }); save(); render(); }
function setCatDefault(cid,loc){ S.catloc[cid]=loc; save(); render(); }

// ================= 啟動 =================
load();
render();
</script>
</body>
</html>
