import crypto from 'node:crypto';

const FALLBACK = {
  national: {
    priceMomentum3m: -3.1,
    auctionClearance: 52.6,
    listingsVs5y: 2.2,
    salesYoY: -2.7,
    lendingQoQ: -5.2,
    sellingSpeed: { current: 39, previous: 28 },
    consumerSentiment: 84.4
  },
  cities: {
    sydney: { name:'Sydney', state:'NSW', priceMomentum3m:-4.7, auctionClearance:52.8, x:78, y:67 },
    melbourne: { name:'Melbourne', state:'VIC', priceMomentum3m:-3.9, auctionClearance:57.3, x:71, y:82 },
    brisbane: { name:'Brisbane', state:'QLD', priceMomentum3m:-2.7, auctionClearance:38.5, x:82, y:43 },
    adelaide: { name:'Adelaide', state:'SA', priceMomentum3m:-1.6, auctionClearance:49.4, x:52, y:70 },
    perth: { name:'Perth', state:'WA', priceMomentum3m:-3.2, auctionClearance:38.1, x:17, y:63 },
    hobart: { name:'Hobart', state:'TAS', priceMomentum3m:-0.2, auctionClearance:null, x:70, y:96 },
    darwin: { name:'Darwin', state:'NT', priceMomentum3m:0.9, auctionClearance:null, x:49, y:16 },
    canberra: { name:'Canberra', state:'ACT', priceMomentum3m:-2.8, auctionClearance:43.1, x:74, y:70 },
    goldcoast: { name:'Gold Coast', state:'QLD', priceMomentum3m:-0.72, auctionClearance:null, score:44, coverage:25, regional:true, sourceName:'realestate.com.au Home Price Report', sourceUpdated:'August 2026' },
    newcastle: { name:'Newcastle', state:'NSW', priceMomentum3m:-2.8, auctionClearance:null, score:27, coverage:25, regional:true, sourceName:'Cotality regional HVI', sourceUpdated:'August 2026' },
    geelong: { name:'Geelong', state:'VIC', priceMomentum3m:-1.11, auctionClearance:null, score:41, coverage:25, regional:true, sourceName:'PropTrack Home Price Index', sourceUpdated:'July 2026' },
    townsville: { name:'Townsville', state:'QLD', priceMomentum3m:-0.25, auctionClearance:null, score:48, coverage:25, regional:true, sourceName:'realestate.com.au Home Price Report', sourceUpdated:'August 2026' },
    cairns: { name:'Cairns', state:'QLD', priceMomentum3m:0.03, auctionClearance:null, score:50, coverage:25, regional:true, sourceName:'realestate.com.au Home Price Report', sourceUpdated:'August 2026' }
  }
};

const URLS = {
  cotalityMonthly: 'https://www.cotality.com/au/insights/articles/high-end-homes-lead-market-downturn-as-affordable-properties-prove-resilient',
  cotalityInsights: 'https://www.cotality.com/au/insights/all-insights',
  cotalityNewsroom: 'https://www.cotality.com/au/newsroom',
  cotalityAuctionFallback: 'https://www.cotality.com/au/press-releases/final-clearance-rates-week-ending-13-september',
  cotalityAuctionTable: 'https://www.cotality.com/au/our-data/auction-results',
  absLending: 'https://www.abs.gov.au/statistics/economy/finance/lending-indicators/latest-release',
  sentiment: 'https://melbourneinstitute.unimelb.edu.au/research/macroeconomics/latest-news/index-of-consumer-sentiment',
  cityValues: 'https://propertyupdate.com.au/the-latest-median-property-prices-in-australias-major-cities/'
};


const RATE_URLS = {
  rbaCash: 'https://www.rba.gov.au/statistics/cash-rate/',
  rbaOverview: 'https://www.rba.gov.au/cash-rate-target-overview.html',
  rbaSchedule: 'https://www.rba.gov.au/schedules-events/board-meeting-schedules.html',
  absCpi: 'https://www.abs.gov.au/statistics/economy/price-indexes-and-inflation/consumer-price-index-australia/latest-release',
  asxFutures: 'https://asx.api.markitdigital.com/asx-research/1.0/derivatives/interest-rate/IB/futures?days=1&height=179&width=179',
  rateWatch: 'https://rbaratewatch.com/rba-meeting/'
};
const RATE_FALLBACK = {
  updatedAt:'2026-09-18T14:49:00+10:00', currentRate:4.35, effectiveDate:'2026-08-12', nextMeeting:'2026-09-29',
  lastMove:{date:'2026-05-06',change:0.25,rate:4.35},
  cpi:{value:3.5,previous:3.8,changePp:-0.3,period:'July 2026',trimmedMean:3.6,nextRelease:'2026-09-30'},
  probabilities:{cut:0.10,hold:27.63,hike:72.27,asOf:'18 Sep 2026, 2:49 pm AEST',source:'RBA Rate Watch · ASX futures'},
  history:[['2006-05-03',5.75],['2006-08-02',6],['2006-11-08',6.25],['2007-08-08',6.5],['2007-11-07',6.75],['2008-02-06',7],['2008-03-05',7.25],['2008-09-03',7],['2008-10-08',6],['2008-11-05',5.25],['2008-12-03',4.25],['2009-02-04',3.25],['2009-04-08',3],['2009-10-07',3.25],['2009-11-04',3.5],['2009-12-02',3.75],['2010-03-03',4],['2010-04-07',4.25],['2010-05-05',4.5],['2010-11-03',4.75],['2011-11-02',4.5],['2011-12-07',4.25],['2012-05-02',3.75],['2012-06-06',3.5],['2012-10-03',3.25],['2012-12-05',3],['2013-05-08',2.75],['2013-08-07',2.5],['2015-02-04',2.25],['2015-05-06',2],['2016-05-04',1.75],['2016-08-03',1.5],['2019-06-05',1.25],['2019-07-03',1],['2019-10-02',0.75],['2020-03-04',0.5],['2020-03-20',0.25],['2020-11-04',0.1],['2022-05-04',0.35],['2022-06-08',0.85],['2022-07-06',1.35],['2022-08-03',1.85],['2022-09-07',2.35],['2022-10-05',2.6],['2022-11-02',2.85],['2022-12-07',3.1],['2023-02-08',3.35],['2023-03-08',3.6],['2023-05-03',3.85],['2023-06-07',4.1],['2023-11-08',4.35],['2025-02-19',4.1],['2025-05-21',3.85],['2025-08-13',3.6],['2026-02-04',3.85],['2026-03-18',4.1],['2026-05-06',4.35]].map(([date,rate])=>({date,rate})),
  futures:[['2026-09-28',4.355],['2026-10-28',4.565],['2026-11-28',4.685],['2026-12-29',4.725],['2027-01-27',4.735],['2027-02-24',4.805],['2027-03-29',4.86],['2027-04-28',4.895],['2027-05-29',4.935],['2027-06-28',4.94],['2027-07-28',4.945],['2027-08-29',4.945],['2027-09-28',4.945]].map(([date,rate])=>({date,rate})),
  meetingPath:[['2026-09-30',4.565],['2026-11-04',4.685],['2026-12-09',4.735],['2027-02-10',4.805],['2027-03-24',4.86],['2027-05-05',4.935],['2027-06-23',4.94],['2027-08-11',4.945]].map(([effectiveDate,impliedRate])=>({effectiveDate,impliedRate}))
};


const MEDIA_RSS_QUERIES = [
  'site:9news.com.au (property OR housing OR mortgage OR "interest rates" OR RBA) Australia when:7d',
  'site:7news.com.au (property OR housing OR mortgage OR "interest rates" OR RBA) Australia when:7d',
  'site:10.com.au/news (property OR housing OR mortgage OR "interest rates" OR RBA) Australia when:7d',
  'site:abc.net.au/news (property OR housing OR mortgage OR "interest rates" OR RBA) Australia when:7d',
  'site:sbs.com.au/news (property OR housing OR mortgage OR "interest rates" OR RBA) Australia when:7d',
  'Australian property market when:7d',
  'Australia housing market house prices when:7d',
  'Australia mortgage rates housing when:7d'
];
const MEDIA_TONE_TERMS = [
  ['property crash',-4],['housing crash',-4],['market crash',-4],['collapse',-3.5],['plunge',-3],['plummet',-3],['slump',-2.6],['downturn',-2.4],['tumble',-2.3],['correction',-1.7],['price falls',-1.8],['prices fall',-1.8],['falling prices',-1.8],['decline',-1.4],['weakening',-1.4],['cooling',-1.2],['mortgage stress',-2.7],['mortgage pain',-2.5],['arrears',-2.4],['defaults',-2.5],['unaffordable',-2.1],['affordability crisis',-2.8],['housing crisis',-2.5],['rental crisis',-2.3],['rate hike',-2.0],['rate rise',-2.0],['higher rates',-1.6],['interest rate pressure',-1.7],['squeeze',-1.4],['pressure',-0.8],['risk',-0.7],['warning',-1.2],['worst',-1.8],['record low',-1.2],
  ['property boom',3.2],['housing boom',3.2],['surge',2.2],['soar',2.5],['soaring',2.5],['rebound',2.4],['recovery',2.0],['rally',2.1],['strong growth',2.1],['price growth',1.5],['prices rise',1.5],['rising prices',1.5],['record high',1.7],['strong demand',1.9],['buyer demand',1.2],['rate cut',2.2],['rate cuts',2.0],['lower rates',1.8],['easing rates',1.7],['confidence lifts',1.7],['confidence rises',1.7],['optimism',1.8],['hot market',1.8],['resilient',1.3],['outperform',1.5]
];
const MEDIA_TOPICS = [
  {key:'rates',label:'Interest rates',terms:['interest rate','cash rate','rate hike','rate rise','rate cut','rba','mortgage rate']},
  {key:'affordability',label:'Affordability',terms:['affordability','unaffordable','first home','deposit','housing cost','home buyer']},
  {key:'mortgage',label:'Mortgage stress',terms:['mortgage stress','arrears','default','repayment','refinance','borrower','household pressure']},
  {key:'prices',label:'Price movements',terms:['house price','home price','property price','dwelling value','price growth','price fall','capital growth','median price']},
  {key:'supply',label:'Listings & supply',terms:['listing','housing supply','stock on market','shortage','new homes','construction','approvals']},
  {key:'rent',label:'Rents',terms:['rent','rental','vacancy']},
  {key:'investors',label:'Investors',terms:['investor','investment property','landlord','negative gearing']}
];

const SOURCE_LIST = [
  { name:'Cotality Housing Chart Pack', detail:'Prices, listings, sales and selling time', url:URLS.cotalityMonthly },
  { name:'Cotality Auction Results', detail:'Latest final auction clearance rates', url:URLS.cotalityAuctionTable },
  { name:'Australian Bureau of Statistics', detail:'Latest Lending Indicators', url:URLS.absLending },
  { name:'Westpac–Melbourne Institute', detail:'Latest Consumer Sentiment', url:URLS.sentiment },
  { name:'Cotality capital-city HVI table', detail:'City 3-month price momentum, republished by Property Update', url:URLS.cityValues },
  { name:'PropTrack / realestate.com.au regional market reports', detail:'Selected regional-city 3-month price momentum for Markets Map', url:'https://www.realestate.com.au/insights/proptrack-home-price-index-august-2026/' }
];

const clamp = (n,min=0,max=100)=>Math.min(max,Math.max(min,n));
const linear = (v,low,high)=>clamp(((v-low)/(high-low))*100);
const DEF = {
  priceMomentum3m:{weight:.25,score:v=>linear(v,-6,6)},
  auctionClearance:{weight:.15,score:v=>linear(v,40,80)},
  listingsVs5y:{weight:.15,score:v=>linear(-v,-20,20)},
  salesYoY:{weight:.10,score:v=>linear(v,-15,15)},
  lendingQoQ:{weight:.15,score:v=>linear(v,-15,15)},
  sellingSpeed:{weight:.10,score:v=>linear(((v.previous-v.current)/v.previous)*100,-50,50)},
  consumerSentiment:{weight:.10,score:v=>linear(v,70,130)}
};

function categoryFor(score){
  if(score<=20)return 'Extreme Fear'; if(score<=40)return 'Fear'; if(score<=60)return 'Neutral'; if(score<=80)return 'Greed'; return 'Extreme Greed';
}
function hasValue(v){
  if(v===null||v===undefined)return false;
  if(typeof v==='number')return Number.isFinite(v);
  if(typeof v==='object')return Object.values(v).every(Number.isFinite);
  return false;
}
function calculatePartial(inputs){
  let weighted=0, coverage=0;
  for(const [k,d] of Object.entries(DEF)) if(hasValue(inputs[k])) { weighted += d.score(inputs[k])*d.weight; coverage += d.weight; }
  const score = coverage ? Math.round(weighted/coverage) : 0;
  return {score, category:categoryFor(score), coverage:Math.round(coverage*100)};
}
function calculateNational(inputs){
  let score=0; for(const [k,d] of Object.entries(DEF)) score += d.score(inputs[k])*d.weight;
  score=Math.round(score); return {score,category:categoryFor(score),coverage:100};
}

async function fetchText(url, ms=8500){
  const controller = new AbortController();
  const timer=setTimeout(()=>controller.abort(),ms);
  try{
    const r=await fetch(url,{headers:{'user-agent':'Mozilla/5.0 (iPhone; CPU iPhone OS 18_0 like Mac OS X) AppleWebKit/605.1.15 Version/18.0 Mobile/15E148 Safari/604.1','accept':'text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8','accept-language':'en-AU,en;q=0.9'},redirect:'follow',signal:controller.signal});
    if(!r.ok) throw new Error(`${r.status} ${url}`);
    return await r.text();
  } finally { clearTimeout(timer); }
}

async function fetchJson(url, ms=8500){
  const controller=new AbortController(); const timer=setTimeout(()=>controller.abort(),ms);
  try{const r=await fetch(url,{headers:{'user-agent':'Mozilla/5.0 PropertyPulseAU/0.4.3','accept':'application/json,text/plain,*/*'},redirect:'follow',signal:controller.signal});if(!r.ok)throw new Error(`${r.status} ${url}`);return await r.json()}finally{clearTimeout(timer)}
}
const MONTH_NUM={Jan:'01',Feb:'02',Mar:'03',Apr:'04',May:'05',Jun:'06',Jul:'07',Aug:'08',Sep:'09',Oct:'10',Nov:'11',Dec:'12',January:'01',February:'02',March:'03',April:'04',June:'06',July:'07',August:'08',September:'09',October:'10',November:'11',December:'12'};
function isoFromRbaDate(s){const m=String(s||'').trim().match(/^(\d{1,2})\s+([A-Za-z]+)\s+(\d{4})$/);if(!m||!MONTH_NUM[m[2]])return null;return `${m[3]}-${MONTH_NUM[m[2]]}-${String(m[1]).padStart(2,'0')}`}
function isoFromSlash(s){const m=String(s||'').trim().match(/^(\d{1,2})\/(\d{1,2})\/(\d{4})$/);return m?`${m[3]}-${String(m[2]).padStart(2,'0')}-${String(m[1]).padStart(2,'0')}`:null}
function meetingSlug(iso){const d=new Date(`${iso}T00:00:00Z`);if(Number.isNaN(d.getTime()))return null;const month=new Intl.DateTimeFormat('en-AU',{month:'long',timeZone:'UTC'}).format(d).toLowerCase();return `${month}-${d.getUTCFullYear()}`}
async function getRbaRates(){
  const text=textify(await fetchText(RATE_URLS.rbaCash)); const rows=[]; const re=/(\d{1,2}\s+(?:Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec)\s+\d{4})\s+([+\-−]?\d+(?:\.\d+)?)(?:\s+to\s+[+\-−]?\d+(?:\.\d+)?)?\s+(\d+(?:\.\d+)?)(?:\s+to\s+\d+(?:\.\d+)?)?/g; let m;
  while((m=re.exec(text))){const date=isoFromRbaDate(m[1]),change=Number(String(m[2]).replace('−','-')),rate=Number(m[3]);if(date&&Number.isFinite(rate)&&Number.isFinite(change))rows.push({date,change,rate})}
  const unique=[...new Map(rows.map(x=>[x.date,x])).values()].sort((a,b)=>a.date.localeCompare(b.date)); if(!unique.length)throw new Error('RBA history parse');
  const latest=unique.at(-1),lastMove=[...unique].reverse().find(x=>Math.abs(x.change)>.0001)||null;
  let nextMeeting=null; try{const ov=textify(await fetchText(RATE_URLS.rbaOverview));const mm=ov.match(/Next update\s+(?:\d{1,2}[.:]\d{2}\s*(?:am|pm),?\s*)?(\d{1,2}\s+[A-Za-z]+\s+\d{4})/i);if(mm)nextMeeting=isoFromRbaDate(mm[1])}catch{}
  return {currentRate:latest.rate,effectiveDate:latest.date,lastMove:lastMove?{date:lastMove.date,change:lastMove.change,rate:lastMove.rate}:null,nextMeeting,history:unique.map(({date,rate})=>({date,rate}))};
}
async function getLatestCpi(){
  const t=textify(await fetchText(RATE_URLS.absCpi)); const m=t.match(/Consumer Price Index \(CPI\) rose\s*([0-9.]+)%,\s*(down|up) from\s*([0-9.]+)%/i)||t.match(/CPI rose\s*([0-9.]+)%,\s*(down|up) from\s*([0-9.]+)%/i); if(!m)throw new Error('CPI parse');
  const value=Number(m[1]),previous=Number(m[3]),period=t.match(/Reference period\s+([A-Za-z]+\s+\d{4})/i)?.[1]||'Latest',trimmed=Number(t.match(/Trimmed mean inflation was\s*([0-9.]+)%/i)?.[1]); const next=t.match(/Next Release\s+(\d{1,2}\/\d{1,2}\/\d{4})/i)?.[1];
  return {value,previous,changePp:Number((value-previous).toFixed(2)),period,trimmedMean:Number.isFinite(trimmed)?trimmed:null,nextRelease:next?isoFromSlash(next):null};
}
async function getAsxFutures(){
  const j=await fetchJson(RATE_URLS.asxFutures); const items=j?.data?.items||[]; const out=items.map(x=>{const px=Number.isFinite(Number(x.pricePreviousSettlement))?Number(x.pricePreviousSettlement):Number(x.priceContract);return {date:String(x.dateExpiry||'').slice(0,10),rate:Number((100-px).toFixed(3)),settlementDate:String(x.datePreviousSettlement||x.dateLastTrade||'').slice(0,10)}}).filter(x=>/^\d{4}-\d{2}-\d{2}$/.test(x.date)&&Number.isFinite(x.rate)&&x.rate>0&&x.rate<20); if(!out.length)throw new Error('ASX futures parse');return out;
}

async function getRbaMeetingDates(){
  const t=textify(await fetchText(RATE_URLS.rbaSchedule));const out=[];
  for(const year of [2026,2027,2028]){
    const marker=`Board meeting schedules ${year}`,i=t.indexOf(marker);if(i<0)continue;const next=t.indexOf('Board meeting schedules ',i+marker.length),block=t.slice(i,next>i?next:undefined);
    const re=/(\d{1,2})[–-](\d{1,2})\s+(February|March|May|June|August|September|November|December)/g;let m;
    while((m=re.exec(block))){const mon=MONTH_NUM[m[3]],decision=`${year}-${mon}-${String(m[2]).padStart(2,'0')}`;out.push({decisionDate:decision,effectiveDate:addDaysIso(decision,1)})}
  }
  return out.sort((a,b)=>a.decisionDate.localeCompare(b.decisionDate));
}
function addDaysIso(iso,n){const d=new Date(`${iso}T00:00:00Z`);d.setUTCDate(d.getUTCDate()+n);return d.toISOString().slice(0,10)}
function monthStartEnd(iso){const d=new Date(`${iso}T00:00:00Z`),y=d.getUTCFullYear(),m=d.getUTCMonth(),start=new Date(Date.UTC(y,m,1)),end=new Date(Date.UTC(y,m+1,0));return {start,end,days:end.getUTCDate(),key:`${y}-${String(m+1).padStart(2,'0')}`}}
function buildMarketMeetingPath(currentRate,meetings,futures,fromDate){
  const fs=(futures||[]).map(x=>({...x,key:String(x.date).slice(0,7)})).filter(x=>Number.isFinite(Number(x.rate))).sort((a,b)=>a.date.localeCompare(b.date));
  const ms=(meetings||[]).filter(x=>x.decisionDate>=fromDate).slice(0,10);let pre=Number(currentRate);const out=[];
  for(let i=0;i<ms.length;i++){
    const m=ms[i],eff=new Date(`${m.effectiveDate}T00:00:00Z`),nextEff=ms[i+1]?new Date(`${ms[i+1].effectiveDate}T00:00:00Z`):null;let chosen=null,method='meeting-month adjusted';
    for(const f of fs){const se=monthStartEnd(f.date);if(se.start>=eff&&(!nextEff||se.end<nextEff)){chosen=f;method='full post-meeting futures month';break}}
    let implied;if(chosen){implied=Number(chosen.rate)}else{chosen=fs.find(f=>f.key===m.effectiveDate.slice(0,7))||fs.find(f=>f.date>=m.effectiveDate);if(chosen){const se=monthStartEnd(chosen.date),day=eff.getUTCDate(),before=Math.max(0,Math.min(se.days,day-1)),after=Math.max(1,se.days-before);implied=(Number(chosen.rate)*se.days-pre*before)/after}else implied=pre}
    implied=Math.max(pre-.75,Math.min(pre+.75,implied));out.push({decisionDate:m.decisionDate,effectiveDate:m.effectiveDate,impliedRate:Number(implied.toFixed(3)),sourceContractDate:chosen?.date||null,method});pre=implied;
  }
  return out;
}
function probabilitiesFromMeetingPath(currentRate,path,settlementDate){
  const next=path?.[0];if(!next||!Number.isFinite(Number(next.impliedRate)))return null;const delta=Number(next.impliedRate)-Number(currentRate),step=.25;let cut=0,hold=0,hike=0;if(delta>=0){hike=Math.max(0,Math.min(100,delta/step*100));hold=100-hike}else{cut=Math.max(0,Math.min(100,-delta/step*100));hold=100-cut}return {cut:Number(cut.toFixed(1)),hold:Number(hold.toFixed(1)),hike:Number(hike.toFixed(1)),asOf:settlementDate?settlementDate:null,source:'ASX 30 Day Interbank Cash Rate Futures · meeting-date adjusted'};
}

async function getRateProbabilities(nextMeeting){
  const slug=meetingSlug(nextMeeting); if(!slug)throw new Error('meeting slug'); const url=`${RATE_URLS.rateWatch}${slug}/`; const t=textify(await fetchText(url));
  let m=t.match(/model estimates a\s*([0-9.]+)% chance of a hold, a\s*([0-9.]+)% chance of a cut, and a\s*([0-9.]+)% chance of a rise/i); let hold,cut,hike;
  if(m){hold=Number(m[1]);cut=Number(m[2]);hike=Number(m[3])}else{const c=t.match(/Cut\s*([0-9.]+)%/i),h=t.match(/Hold\s*([0-9.]+)%/i),r=t.match(/Rise\s*([0-9.]+)%/i);if(!c||!h||!r)throw new Error('probability parse');cut=Number(c[1]);hold=Number(h[1]);hike=Number(r[1])}
  const as=t.match(/Updated\s+(\d{1,2}\s+[A-Za-z]{3},\s*[0-9:]+\s*(?:am|pm)\s*(?:AEST|AEDT))/i)?.[1]||null; return {cut,hold,hike,asOf:as,source:'RBA Rate Watch · ASX futures',url};
}
async function buildRates(){
  const notes=[]; let rba,cpi,futures,probabilities,meetings=[];
  const [rbaR,cpiR,futR,meetR]=await Promise.allSettled([getRbaRates(),getLatestCpi(),getAsxFutures(),getRbaMeetingDates()]);
  rba=rbaR.status==='fulfilled'?rbaR.value:{currentRate:RATE_FALLBACK.currentRate,effectiveDate:RATE_FALLBACK.effectiveDate,lastMove:RATE_FALLBACK.lastMove,nextMeeting:RATE_FALLBACK.nextMeeting,history:RATE_FALLBACK.history};if(rbaR.status!=='fulfilled')notes.push('RBA live parser fallback used');
  cpi=cpiR.status==='fulfilled'?cpiR.value:RATE_FALLBACK.cpi;if(cpiR.status!=='fulfilled')notes.push('ABS CPI fallback used');
  futures=futR.status==='fulfilled'?futR.value:RATE_FALLBACK.futures;if(futR.status!=='fulfilled')notes.push('ASX futures fallback used');
  meetings=meetR.status==='fulfilled'?meetR.value:[];if(meetR.status!=='fulfilled')notes.push('RBA meeting schedule unavailable');
  const meeting=rba.nextMeeting||RATE_FALLBACK.nextMeeting,knownMeetings=meetings.length?meetings:[{decisionDate:'2026-09-29',effectiveDate:'2026-09-30'},{decisionDate:'2026-11-03',effectiveDate:'2026-11-04'},{decisionDate:'2026-12-08',effectiveDate:'2026-12-09'},{decisionDate:'2027-02-09',effectiveDate:'2027-02-10'},{decisionDate:'2027-03-23',effectiveDate:'2027-03-24'},{decisionDate:'2027-05-04',effectiveDate:'2027-05-05'},{decisionDate:'2027-06-22',effectiveDate:'2027-06-23'},{decisionDate:'2027-08-10',effectiveDate:'2027-08-11'}];
  const settlementDate=futures.map(x=>x.settlementDate).filter(Boolean).sort().at(-1)||null,meetingPath=buildMarketMeetingPath(rba.currentRate,knownMeetings,futures,meeting||new Date().toISOString().slice(0,10));
  try{probabilities=await getRateProbabilities(meeting)}catch{probabilities=probabilitiesFromMeetingPath(rba.currentRate,meetingPath,settlementDate);notes.push('Direct ASX meeting-path probability estimate used')}if(!probabilities)probabilities=(meeting===RATE_FALLBACK.nextMeeting)?RATE_FALLBACK.probabilities:{cut:null,hold:null,hike:null,asOf:null,source:'Unavailable'};
  const horizonDate=new Date();horizonDate.setUTCMonth(horizonDate.getUTCMonth()+6);const target=meetingPath.find(x=>new Date(`${x.effectiveDate}T00:00:00Z`)>=horizonDate)||meetingPath.at(-1);const targetRate=Number(target?.impliedRate),delta=Number.isFinite(targetRate)?targetRate-rba.currentRate:0,bias=delta>.125?'hike':delta<-.125?'cut':'neutral';
  return {updatedAt:new Date().toISOString(),...rba,cpi,futures,meetingPath,probabilities,outlook:{bias,average6to12:Number.isFinite(targetRate)?targetRate:rba.currentRate,text:Number.isFinite(targetRate)?`ASX market pricing implies a cash-rate path near ${targetRate.toFixed(2)}% by ${target.effectiveDate}`:'Market direction over the next 6–12 months'},forecastMethod:'ASX 30 Day Interbank Cash Rate Futures converted to a meeting-date path using official RBA meeting dates',marketAsOf:settlementDate,notes,sources:{rba:RATE_URLS.rbaCash,cpi:RATE_URLS.absCpi,asx:RATE_URLS.asxFutures,rbaSchedule:RATE_URLS.rbaSchedule,probabilities:'https://www.asx.com.au/markets/trade-our-derivatives-market/futures-market/rba-rate-tracker'}};
}


function decodeXml(s=''){
  return String(s).replace(/<!\[CDATA\[([\s\S]*?)\]\]>/g,'$1').replace(/&amp;/g,'&').replace(/&quot;/g,'"').replace(/&apos;|&#39;/g,"'").replace(/&lt;/g,'<').replace(/&gt;/g,'>').replace(/&#(\d+);/g,(_,n)=>String.fromCharCode(Number(n))).replace(/\s+/g,' ').trim();
}
function cleanMediaTitle(title,source){
  let t=decodeXml(title).replace(/<[^>]+>/g,' ').replace(/\s+/g,' ').trim();
  if(source){const suffix=` - ${source}`;if(t.toLowerCase().endsWith(suffix.toLowerCase()))t=t.slice(0,-suffix.length).trim();}
  return t;
}

function normaliseMediaSource(name=''){
  const s=String(name).trim(),l=s.toLowerCase();
  if(l.includes('9news')||l.includes('nine news'))return '9News';
  if(l.includes('7news')||l.includes('seven news'))return '7NEWS';
  if(l.includes('10 news')||l.includes('10news')||l.includes('network 10')||l.includes('10.com.au'))return '10 News';
  if(l.includes('abc news')||l==='abc')return 'ABC News';
  if(l.includes('sbs news')||l==='sbs')return 'SBS News';
  return s||'Unknown source';
}
function parseNewsRss(xml){
  const out=[];for(const m of String(xml).matchAll(/<item>([\s\S]*?)<\/item>/gi)){const b=m[1],gm=tag=>{const x=b.match(new RegExp(`<${tag}(?:\\s[^>]*)?>([\\s\\S]*?)<\\/${tag}>`,'i'));return x?decodeXml(x[1]):''};const source=normaliseMediaSource(gm('source')||'Unknown source'),title=cleanMediaTitle(gm('title'),source),link=gm('link'),pub=gm('pubDate'),date=pub?new Date(pub):null;if(!title||!date||Number.isNaN(date.getTime()))continue;out.push({title,source,link,publishedAt:date.toISOString()});}return out;
}
function mediaHeadlineScore(title){
  const t=String(title||'').toLowerCase();let raw=0,matched=0;for(const [phrase,w] of MEDIA_TONE_TERMS){if(t.includes(phrase)){raw+=w;matched++}}if(!matched)return 50;raw=Math.max(-6,Math.min(6,raw));return Math.round(Math.max(0,Math.min(100,50+raw*7.5))*10)/10;
}
function mediaPrimaryTopic(title){const t=String(title||'').toLowerCase();let best=null,bestHits=0;for(const topic of MEDIA_TOPICS){let hits=0;for(const term of topic.terms)if(t.includes(term))hits++;if(hits>bestHits){best=topic;bestHits=hits}}return best||{key:'other',label:'Other'};}
function weightedAverage(rows,key='score'){
  let total=0,w=0;for(const r of rows){const age=Math.max(0,(Date.now()-new Date(r.publishedAt).getTime())/3600000),weight=Math.pow(.5,age/72);total+=Number(r[key])*weight;w+=weight}return w?total/w:null;
}
function mediaToneLabel(score){const tone=Number(score);if(tone<43)return 'Fear-leaning';if(tone>57)return 'Greed-leaning';return 'Neutral';}
function mediaNarrativeTheme(driver,rows=[]){const sorted=[...rows].sort((a,b)=>new Date(b.publishedAt)-new Date(a.publishedAt)),example=sorted.find(x=>x.title&&x.source)||sorted[0];return{label:driver.label,count:driver.count,sourceCount:new Set(rows.map(x=>x.source)).size,tone:mediaToneLabel(driver.averageScore),toneScore:Number(Number(driver.averageScore).toFixed(1)),exampleHeadline:example?.title||'',exampleSource:example?.source||''};}
async function readMediaHistory(){const h=await readBlobJson('property-pulse/media-history.json');return Array.isArray(h)?h:[];}
async function saveMediaHistory(entry){let h=await readMediaHistory();const idx=h.findIndex(x=>x.date===entry.date);if(idx>=0)h[idx]=entry;else h.push(entry);h=h.sort((a,b)=>a.date.localeCompare(b.date)).slice(-370);await writeBlobJson('property-pulse/media-history.json',h);return h;}
async function buildMedia(propertyScore=null){
  let items=[];const failures=[];
  for(const q of MEDIA_RSS_QUERIES){try{const url=`https://news.google.com/rss/search?q=${encodeURIComponent(q)}&hl=en-AU&gl=AU&ceid=AU:en`;items.push(...parseNewsRss(await fetchText(url,9000)))}catch(e){failures.push(String(e?.message||e))}}
  const cutoff=Date.now()-7*86400000,seen=new Set(),sourceSeen=new Map();items=items.filter(x=>new Date(x.publishedAt).getTime()>=cutoff).sort((a,b)=>new Date(b.publishedAt)-new Date(a.publishedAt)).filter(x=>{const k=x.title.toLowerCase().replace(/[^a-z0-9]+/g,' ').trim();if(!k||seen.has(k))return false;const n=sourceSeen.get(x.source)||0;if(n>=35)return false;seen.add(k);sourceSeen.set(x.source,n+1);return true}).slice(0,300);
  let history=await readMediaHistory().catch(()=>[]);
  if(!items.length){const last=history.at(-1);return last?{...last,history,updatedAt:new Date().toISOString(),mode:'Cached media history',stale:true,failures}:{unavailable:true,score:null,updatedAt:new Date().toISOString(),articleCount:0,sourceCount:0,coverage:0,drivers:[],narratives:[],sources:[],history:[],mode:'Media feed unavailable',failures};}
  const scored=items.map(x=>({...x,score:mediaHeadlineScore(x.title),topic:mediaPrimaryTopic(x.title)}));
  const articleAverage=weightedAverage(scored);
  const bySource=new Map();for(const x of scored){if(!bySource.has(x.source))bySource.set(x.source,[]);bySource.get(x.source).push(x)}
  const sourceAverages=[...bySource.values()].map(rows=>weightedAverage(rows)).filter(Number.isFinite);const sourceBalanced=sourceAverages.length?sourceAverages.reduce((a,b)=>a+b,0)/sourceAverages.length:articleAverage;const score=Math.round((articleAverage*.7+sourceBalanced*.3));
  const topicCounts=new Map();for(const x of scored){const k=x.topic.key;if(!topicCounts.has(k))topicCounts.set(k,{label:x.topic.label,rows:[]});topicCounts.get(k).rows.push(x)}
  const drivers=[...topicCounts.entries()].map(([key,g])=>({key,label:g.label,count:g.rows.length,share:g.rows.length/scored.length*100,averageScore:weightedAverage(g.rows)})).sort((a,b)=>b.count-a.count||Math.abs(50-a.averageScore)-Math.abs(50-b.averageScore)).slice(0,6).map(x=>({...x,share:Number(x.share.toFixed(1)),averageScore:Number(x.averageScore.toFixed(1))}));
  const last24=scored.filter(x=>Date.now()-new Date(x.publishedAt).getTime()<=86400000).length,older=Math.max(0,scored.length-last24),baseline=older/6,ratio=baseline>0?last24/baseline:(last24?2:1),pressureLabel=ratio>=1.4?'High':ratio<=.65?'Low':'Normal',meter=Math.round(Math.max(8,Math.min(100,ratio/2*100)));const pressureText=pressureLabel==='High'?`Property-news volume in the last 24 hours is ${Math.round((ratio-1)*100)}% above the rest-of-week daily average.`:pressureLabel==='Low'?`Property-news volume in the last 24 hours is ${Math.round((1-ratio)*100)}% below the rest-of-week daily average.`:'Property-news volume in the last 24 hours is close to the rest-of-week daily average.';
  const sourceSummary=[...bySource.entries()].map(([name,rows])=>({name,count:rows.length})).sort((a,b)=>b.count-a.count||a.name.localeCompare(b.name));
  const coverage=Math.round(Math.min(100,(Math.min(scored.length,40)/40)*60+(Math.min(bySource.size,10)/10)*40));
  const date=new Date().toISOString().slice(0,10),entry={date,updatedAt:new Date().toISOString(),score,category:categoryFor(score),propertyScore:Number.isFinite(Number(propertyScore))?Math.round(Number(propertyScore)):null,articleCount:scored.length,sourceCount:bySource.size,coverage,pressure:{label:pressureLabel,ratio:Number(ratio.toFixed(2)),meter,text:pressureText}};
  history=await saveMediaHistory(entry).catch(()=>{const x=history.filter(h=>h.date!==date);return [...x,entry].sort((a,b)=>a.date.localeCompare(b.date)).slice(-370)});
  const previous=history.filter(x=>x.date<date).at(-1),target7=new Date(Date.now()-7*86400000).toISOString().slice(0,10),weekBase=history.filter(x=>x.date<=target7).at(-1);const movement={delta1d:previous?score-Number(previous.score):null,delta7d:weekBase?score-Number(weekBase.score):null};
  const narratives=drivers.slice(0,4).map(driver=>mediaNarrativeTheme(driver,scored.filter(x=>x.topic?.key===driver.key)));
  return {updatedAt:entry.updatedAt,score,category:entry.category,articleCount:entry.articleCount,sourceCount:entry.sourceCount,coverage,windowDays:7,movement,pressure:entry.pressure,drivers,narratives:narratives.slice(0,4),sources:sourceSummary.slice(0,12),history,methodology:{window:'7-day rolling headlines',recency:'72-hour half-life',sourceBalance:'30% equal-source average',tone:'Fixed headline lexicon',narratives:'Recurring topic counts with recent example headlines'},mode:'Live media sentiment',failures};
}

function textify(html){
  return html.replace(/<script[\s\S]*?<\/script>/gi,' ').replace(/<style[\s\S]*?<\/style>/gi,' ').replace(/<[^>]+>/g,' ')
    .replace(/&nbsp;/gi,' ').replace(/&amp;/gi,'&').replace(/&#39;|&apos;/gi,"'").replace(/&quot;/gi,'"').replace(/&ndash;|&minus;/gi,'-').replace(/\s+/g,' ').trim();
}
const num=s=>Number(String(s).replace(/[,−]/g,m=>m==='−'?'-':''));
function section(text,start,end){
  const low=text.toLowerCase(), a=low.indexOf(start.toLowerCase()); if(a<0)return '';
  const b=end?low.indexOf(end.toLowerCase(),a+start.length):-1; return text.slice(a,b>a?b:undefined);
}
function firstHrefNear(html, phrase, fallback){
  const i=html.toLowerCase().indexOf(phrase.toLowerCase()); if(i<0)return fallback;
  const chunk=html.slice(Math.max(0,i-3000),i+800); const links=[...chunk.matchAll(/href=["']([^"']+)["']/gi)];
  let href=links.at(-1)?.[1]; if(!href)return fallback; if(href.startsWith('/'))href=`https://www.cotality.com${href}`; return href.startsWith('http')?href:fallback;
}

async function getNationalMonthly(){
  let url=URLS.cotalityMonthly;
  try{ url=firstHrefNear(await fetchText(URLS.cotalityInsights),'Monthly Housing Chart Pack',url); }catch{}
  const text=textify(await fetchText(url));
  const out={};
  let m=text.match(/National dwelling values (?:fell|declined)\s*([0-9.]+)% over the three months/i); if(m)out.priceMomentum3m=-num(m[1]);
  else if((m=text.match(/National dwelling values (?:rose|increased)\s*([0-9.]+)% over the three months/i)))out.priceMomentum3m=num(m[1]);
  m=text.match(/National annual sales (?:fell|declined)\s*([0-9.]+)%/i); if(m)out.salesYoY=-num(m[1]);
  else if((m=text.match(/National annual sales (?:rose|increased)\s*([0-9.]+)%/i)))out.salesYoY=num(m[1]);
  m=text.match(/([0-9.]+)% above the five-year average/i); if(m)out.listingsVs5y=num(m[1]);
  else if((m=text.match(/([0-9.]+)% below the five-year average/i)))out.listingsVs5y=-num(m[1]);
  m=text.match(/median time on market[^.]{0,130}?(\d+)\s*days[^.]{0,100}?(\d+)\s*days a year ago/i);
  if(m)out.sellingSpeed={current:num(m[1]),previous:num(m[2])};
  return {url, ...out};
}

async function getAuctionData(){
  let national=FALLBACK.national.auctionClearance, pressUrl=URLS.cotalityAuctionFallback;
  try{
    const newsroom=await fetchText(URLS.cotalityNewsroom); pressUrl=firstHrefNear(newsroom,'Final Clearance',pressUrl);
    const t=textify(await fetchText(pressUrl));
    const m=t.match(/weighted average(?: final)?(?: clearance rate)?[^0-9]{0,90}(?:to|at|of)?\s*([0-9.]+)%/i)
      ||t.match(/combined capital city clearance rate[^0-9]{0,100}([0-9.]+)%/i);
    if(m)national=num(m[1]);
  }catch{}
  const cityRates={};
  try{
    const t=textify(await fetchText(URLS.cotalityAuctionTable));
    const names=['Sydney','Melbourne','Brisbane','Adelaide','Perth','Canberra'];
    for(let i=0;i<names.length;i++){
      const name=names[i], start=t.indexOf(name); if(start<0)continue;
      let end=t.length; for(const other of names){const j=t.indexOf(other,start+name.length);if(j>start&&j<end)end=j;}
      const block=t.slice(start,Math.min(end,start+700)); const p=block.match(/([0-9]{1,2}(?:\.[0-9])?)%/);
      if(p)cityRates[name.toLowerCase()]=num(p[1]);
    }
  }catch{}
  return {national, cityRates, pressUrl};
}

async function getLending(){
  const t=textify(await fetchText(URLS.absLending));
  let m=t.match(/value (?:of total new home loans )?(?:fell|decreased)\s*([0-9.]+)%/i)||t.match(/value fell\s*([0-9.]+)%/i); if(m)return -num(m[1]);
  m=t.match(/value (?:of total new home loans )?(?:rose|increased)\s*([0-9.]+)%/i); if(m)return num(m[1]);
  throw new Error('lending parse');
}
async function getSentiment(){
  const t=textify(await fetchText(URLS.sentiment));
  let m=t.match(/Consumer Sentiment Index[^.]{0,180}?(?:to|at)\s*([0-9]{2,3}(?:\.[0-9]+)?)/i)||t.match(/Index (?:declined|rose|increased|fell)[^.]{0,100}?to\s*([0-9]{2,3}(?:\.[0-9]+)?)/i);
  if(m)return num(m[1]); throw new Error('sentiment parse');
}

async function getCityValues(){
  const cityValues={};
  try{
    const t=textify(await fetchText(URLS.cityValues));
    const cityNames=['Melbourne','Sydney','Brisbane','Adelaide','Perth','Hobart','Darwin','Canberra'];
    for(let i=0;i<cityNames.length;i++){
      const name=cityNames[i], start=t.indexOf(`${name}'s`); if(start<0)continue;
      let end=t.length; for(const other of cityNames){const j=t.indexOf(`${other}'s`,start+name.length);if(j>start&&j<end)end=j;}
      const block=t.slice(start,Math.min(end,start+1500));
      const row=block.match(/All (?:Capital city )?dwellings\s*\$[0-9,]+\s*([-−]?[0-9.]+)%\s*([-−]?[0-9.]+)%\s*([-−]?[0-9.]+)%/i);
      if(row)cityValues[name.toLowerCase()]={mom:num(row[1]),qoq:num(row[2]),annual:num(row[3])};
    }
  }catch{}
  return cityValues;
}

async function buildMarket(){
  const inputs=structuredClone(FALLBACK.national), notes=[], sources=structuredClone(SOURCE_LIST);
  const sourceStatus=Object.fromEntries(Object.keys(DEF).map(k=>[k,{status:'fallback'}]));
  const [monthly,auction,lending,sentiment,cityValues]=await Promise.allSettled([getNationalMonthly(),getAuctionData(),getLending(),getSentiment(),getCityValues()]);
  if(monthly.status==='fulfilled'){ Object.assign(inputs,monthly.value); delete inputs.url; sources[0].url=monthly.value.url; for(const k of ['priceMomentum3m','listingsVs5y','salesYoY','sellingSpeed'])if(monthly.value[k]!==undefined)sourceStatus[k]={status:'live'}; } else notes.push('Housing chart fallback used');
  if(auction.status==='fulfilled'){ inputs.auctionClearance=auction.value.national; sources[1].url=auction.value.pressUrl; sourceStatus.auctionClearance={status:'live'}; } else notes.push('Auction fallback used');
  if(lending.status==='fulfilled'){inputs.lendingQoQ=lending.value;sourceStatus.lendingQoQ={status:'live'}} else notes.push('ABS lending fallback used');
  if(sentiment.status==='fulfilled'){inputs.consumerSentiment=sentiment.value;sourceStatus.consumerSentiment={status:'live'}} else notes.push('Consumer sentiment fallback used');

  const cities={};
  for(const [key,base] of Object.entries(FALLBACK.cities)){
    const cv=cityValues.status==='fulfilled'?cityValues.value[key]:null;
    const auctionRate=auction.status==='fulfilled'?(auction.value.cityRates[key]??base.auctionClearance):base.auctionClearance;
    const cityInputs={ priceMomentum3m:cv?.qoq??base.priceMomentum3m, auctionClearance:auctionRate, lendingQoQ:inputs.lendingQoQ, consumerSentiment:inputs.consumerSentiment };
    if(auctionRate===null)delete cityInputs.auctionClearance;
    cities[key]={...base, priceMomentum3m:cityInputs.priceMomentum3m, auctionClearance:auctionRate, annualGrowth:cv?.annual??null, ...calculatePartial(cityInputs)};
  }
  const national=calculateNational(inputs);
  const payload={
    updatedAt:new Date().toISOString(),
    mode:notes.length?'Live refresh · partial fallback':'Live refresh',
    inputs,national,cities,notes,sources,sourceStatus,
    sourcePeriods:{priceMomentum3m:'latest published 3 months',auctionClearance:'latest final week',listingsVs5y:'latest published',salesYoY:'latest published year',lendingQoQ:'latest published quarter',sellingSpeed:'latest published',consumerSentiment:'latest monthly'}
  };
  const cloud=await maybeSaveHistory(payload).catch(()=>({ready:false,saved:false}));
  return {...payload,cloudHistory:cloud};
}

const KNOWN = {
  'bogangar':{postcode:'2488',state:'NSW'},'tweed heads':{postcode:'2485',state:'NSW'},'palm beach':{postcode:'4221',state:'QLD'},
  'burleigh heads':{postcode:'4220',state:'QLD'},'southport':{postcode:'4215',state:'QLD'},'surfers paradise':{postcode:'4217',state:'QLD'},
  'broadbeach':{postcode:'4218',state:'QLD'},'robina':{postcode:'4226',state:'QLD'},'coolangatta':{postcode:'4225',state:'QLD'},
  'brisbane city':{postcode:'4000',state:'QLD'},'new farm':{postcode:'4005',state:'QLD'},'paddington':{postcode:'4064',state:'QLD'},
  'sydney':{postcode:'2000',state:'NSW'},'melbourne':{postcode:'3000',state:'VIC'},'adelaide':{postcode:'5000',state:'SA'},'perth':{postcode:'6000',state:'WA'},
  'hobart':{postcode:'7000',state:'TAS'},'darwin city':{postcode:'0800',state:'NT'},'canberra city':{postcode:'2601',state:'ACT'}
};
function inferState(postcode){
  const n=Number(postcode);
  if((n>=200&&n<=299)||(n>=800&&n<=899)||(n>=900&&n<=999))return 'NT';
  if((n>=2600&&n<=2618)||(n>=2900&&n<=2920))return 'ACT';
  if((n>=1000&&n<=2599)||(n>=2619&&n<=2899)||(n>=2921&&n<=2999))return 'NSW';
  if((n>=3000&&n<=3999)||(n>=8000&&n<=8999))return 'VIC';
  if((n>=4000&&n<=4999)||(n>=9000&&n<=9999))return 'QLD';
  if(n>=5000&&n<=5999)return 'SA'; if(n>=6000&&n<=6999)return 'WA'; if(n>=7000&&n<=7999)return 'TAS'; return null;
}
function slugify(s){return s.toLowerCase().normalize('NFKD').replace(/[’']/g,'').replace(/&/g,'and').replace(/[^a-z0-9]+/g,'-').replace(/^-|-$/g,'');}
const POSTCODE_LOOKUP_URL='https://raw.githubusercontent.com/schappim/australian-postcodes/master/data/lookup/postcodes-lookup.csv';
let postcodeLookupCache=null, postcodeLookupLoadedAt=0;
function titleCaseSuburb(s){return String(s||'').toLowerCase().replace(/\b([a-z])/g,m=>m.toUpperCase()).replace(/\bMc([a-z])/g,(_,c)=>'Mc'+c.toUpperCase());}
function normaliseSuburbName(s){return String(s||'').trim().toUpperCase().replace(/[’']/g,"'").replace(/\s+/g,' ');}
async function loadPostcodeLookup(){
  if(postcodeLookupCache && Date.now()-postcodeLookupLoadedAt<6*60*60*1000)return postcodeLookupCache;
  const csv=await fetchText(POSTCODE_LOOKUP_URL,9000);
  const rows=String(csv).split(/\r?\n/).slice(1).map(line=>{
    const parts=line.split(','); if(parts.length<3)return null;
    const postcode=String(parts[0]||'').replace(/^\uFEFF/,'').trim().padStart(4,'0');
    const suburb=String(parts[1]||'').trim(); const state=String(parts[2]||'').trim().toUpperCase();
    if(!/^\d{4}$/.test(postcode)||!suburb||!/^(ACT|NSW|NT|QLD|SA|TAS|VIC|WA)$/.test(state))return null;
    return {name:titleCaseSuburb(suburb),postcode,state};
  }).filter(Boolean);
  const seen=new Set(); postcodeLookupCache=rows.filter(r=>{const k=`${r.name}|${r.state}|${r.postcode}`;if(seen.has(k))return false;seen.add(k);return true});
  postcodeLookupLoadedAt=Date.now(); return postcodeLookupCache;
}
function parseSuburbQuery(query){
  const clean=String(query||'').trim().replace(/,/g,' ').replace(/\s+/g,' '); if(!clean)return null;
  const full=clean.match(/^(.+?)(?:\s+(NSW|VIC|QLD|SA|WA|TAS|NT|ACT))?\s+(\d{4})$/i);
  if(full){const inferred=inferState(full[3]);const state=(full[2]||inferred)?.toUpperCase();if(!state)return null;let name=full[1].trim();if(/\b(NSW|VIC|QLD|SA|WA|TAS|NT|ACT)$/i.test(name))name=name.replace(/\s+(NSW|VIC|QLD|SA|WA|TAS|NT|ACT)$/i,'').trim();return {kind:'exact',parsed:{name,postcode:full[3],state}};}
  if(/^\d{4}$/.test(clean))return {kind:'postcode',postcode:clean};
  const nameState=clean.match(/^(.+?)\s+(NSW|VIC|QLD|SA|WA|TAS|NT|ACT)$/i);
  if(nameState)return {kind:'name',name:nameState[1].trim(),state:nameState[2].toUpperCase()};
  return {kind:'name',name:clean,state:null};
}
async function resolveSuburbQuery(query){
  const parsedQuery=parseSuburbQuery(query); if(!parsedQuery)return {error:'Enter a suburb name or 4-digit postcode.',status:400};
  if(parsedQuery.kind==='exact')return {parsed:parsedQuery.parsed};
  let rows=[];
  try{rows=await loadPostcodeLookup()}catch(e){rows=[]}
  let matches=[];
  if(parsedQuery.kind==='postcode'){
    matches=rows.filter(r=>r.postcode===parsedQuery.postcode);
  }else{
    const wanted=normaliseSuburbName(parsedQuery.name);
    matches=rows.filter(r=>normaliseSuburbName(r.name)===wanted && (!parsedQuery.state||r.state===parsedQuery.state));
  }
  if(!matches.length && parsedQuery.kind==='name'){
    const known=KNOWN[String(parsedQuery.name).toLowerCase()];
    if(known && (!parsedQuery.state||known.state===parsedQuery.state))matches=[{name:titleCaseSuburb(parsedQuery.name),postcode:known.postcode,state:known.state}];
    if(!matches.length&&rows.length){
      const wanted=normaliseSuburbName(parsedQuery.name);
      const fuzzy=rows.filter(r=>(normaliseSuburbName(r.name).startsWith(wanted)||normaliseSuburbName(r.name).includes(wanted))&&(!parsedQuery.state||r.state===parsedQuery.state));
      if(fuzzy.length<=8)matches=fuzzy;
    }
  }
  const seen=new Set();matches=matches.filter(r=>{const k=`${r.name}|${r.state}|${r.postcode}`;if(seen.has(k))return false;seen.add(k);return true}).sort((a,b)=>a.state.localeCompare(b.state)||a.postcode.localeCompare(b.postcode)||a.name.localeCompare(b.name));
  if(matches.length===1)return {parsed:matches[0]};
  if(matches.length>1)return {needsChoice:true,query:String(query),choices:matches.slice(0,30),message:parsedQuery.kind==='postcode'?`That postcode covers ${matches.length} suburbs/localities. Choose one:`:`There is more than one match for “${parsedQuery.name}”. Choose one:`};
  return {error:parsedQuery.kind==='postcode'?`No suburb was found for postcode ${parsedQuery.postcode}.`:`No exact suburb match was found for “${parsedQuery.name}”. Try the suburb spelling or postcode.`,status:404};
}

async function suggestSuburbs(query){
  const clean=String(query||'').trim(); if(clean.length<2)return [];
  let rows=[]; try{rows=await loadPostcodeLookup()}catch{}
  const q=normaliseSuburbName(clean.replace(/\b(NSW|VIC|QLD|SA|WA|TAS|NT|ACT)\b/ig,'').replace(/\d{4}/g,'').trim());
  const pc=(clean.match(/\b(\d{4})\b/)||[])[1]||null;
  const scored=[];
  for(const r of rows){
    const n=normaliseSuburbName(r.name); let score=999;
    if(pc&&r.postcode===pc)score=0;
    else if(q&&n===q)score=0;
    else if(q&&n.startsWith(q))score=1+(n.length-q.length)/100;
    else if(q&&n.includes(q))score=3+n.indexOf(q)/100;
    else continue;
    scored.push({r,score});
  }
  // Keep known aliases available even if the remote postcode CSV is temporarily unavailable.
  for(const [name,k] of Object.entries(KNOWN)){
    const n=normaliseSuburbName(name); if((q&&n.startsWith(q))||(pc&&k.postcode===pc))scored.push({r:{name:titleCaseSuburb(name),postcode:k.postcode,state:k.state},score:1.5});
  }
  const seen=new Set(); return scored.sort((x,y)=>x.score-y.score||x.r.name.localeCompare(y.r.name)).map(x=>x.r).filter(r=>{const k=`${r.name}|${r.state}|${r.postcode}`;if(seen.has(k))return false;seen.add(k);return true}).slice(0,8);
}

const moneyNum=s=>{const t=String(s||'').replace(/[$,\s]/g,'').toLowerCase();const m=t.match(/^(-?[0-9.]+)([mk])?$/);if(!m)return NaN;const n=Number(m[1]);return m[2]==='m'?n*1e6:m[2]==='k'?n*1e3:n};
function completeLocal(p){return p&&Number.isFinite(p.median)&&Number.isFinite(p.annualGrowth)&&Number.isFinite(p.days);}
function parseAnnualHistoryBlock(block){
  if(!block)return [];
  const out=[]; const re=/\b(20\d{2}(?:YTD\*)?)\s+\$([0-9,]+)\s+([0-9,]+)/g; let m;
  while((m=re.exec(block)))out.push({period:m[1],median:moneyNum(m[2]),sales:num(m[3]),ytd:/YTD/i.test(m[1])});
  return out.filter(x=>Number.isFinite(x.median)).sort((a,b)=>String(a.period).localeCompare(String(b.period)));
}
function parseHeatmapsPriceHistory(text){
  const block=section(text,'Price history','Socio-demographic context'); if(!block)return null;
  const houseBlock=section(block,'House median price','Unit median price');
  const unitBlock=section(block,'Unit median price');
  const houses=parseAnnualHistoryBlock(houseBlock), units=parseAnnualHistoryBlock(unitBlock);
  if(!houses.length&&!units.length)return null;
  return {annual:{houses,units},quarterly:null,source:'Heatmaps.com.au',note:'Annual observations plus the current completed-quarter YTD result where published.'};
}
function parseHeatmapsBlock(block){
  if(!block)return null;const out={median:null,annualGrowth:null,rent:null,yield:null,sold:null,days:null,stockPct:null,listings:null,totalStock:null};let m;
  m=block.match(/Median price[^$]{0,80}\$([0-9,]+)/i);if(m)out.median=moneyNum(m[1]);
  m=block.match(/Price growth[^%]{0,100}?([+\-−][0-9.]+)%/i)||block.match(/Price growth[^%]{0,100}?([0-9.]+)%/i);if(m){out.annualGrowth=num(m[1]);out.growthPeriod='Past 12 months';}
  m=block.match(/Median rent[^$]{0,80}\$([0-9,]+)\/week/i);if(m)out.rent=num(m[1]);
  m=block.match(/Gross yield\s+Q\d\s+20\d{2}\s+([0-9.]+)%/i)||block.match(/Gross yield[^%]{0,80}?([0-9.]+)%/i);if(m)out.yield=num(m[1]);
  m=block.match(/Sales in\s+20\d{2}YTD\*?\s+([0-9,]+)/i)||block.match(/Sales in[^0-9]{0,80}?([0-9,]+)\s+Days on market/i);if(m)out.sold=num(m[1]);
  m=block.match(/Days on market\s+Q\d\s+20\d{2}\s+([0-9,]+)/i)||block.match(/Days on market[^0-9]{0,80}?([0-9,]+)\s+Stock on Market/i);if(m)out.days=num(m[1]);
  m=block.match(/Stock on Market[^%]{0,120}?([0-9.]+)%\s*\(([0-9,]+)\)\s*listed/i);if(m){out.stockPct=num(m[1]);out.listings=num(m[2]);}
  m=block.match(/Total (?:Houses|Units)\s*\(20\d{2} estimate\)[^0-9]{0,80}([0-9,]+)/i)||block.match(/Total (?:Houses|Units)[^0-9]{0,100}?([0-9,]+)(?=\s|$)/i);if(m)out.totalStock=num(m[1]);
  return out;
}
function parseHeatmaps(text,parsed,url){
  const snap=section(text,'Market snapshot','Investment signals')||text;const houses=parseHeatmapsBlock(section(snap,'Houses','Units'));const units=parseHeatmapsBlock(section(snap,'Units','Investment signals')||section(snap,'Units'));
  const refresh=(text.match(/Last data refreshed:\s*([0-9]{4}-[A-Z]{3}-[0-9]{2})/i)||text.match(/Profile data refreshed\s*([^\.]{4,40})/i)||[])[1]||'Latest available';
  const profileName=(text.match(/Australian suburb property profile\s+(.+?)\s+(NSW|VIC|QLD|SA|WA|TAS|NT|ACT)\s+\d{4}/i)||[])[1]||parsed.name;
  if(![houses,units].some(completeLocal))return null;
  const priceHistory=parseHeatmapsPriceHistory(text);
  const growthLabel=(text.match(/Price growth\s+(20\d{2}YTD\*?\s+vs\s+20\d{2})/i)||[])[1]||'Latest published YTD vs prior year';
  if(houses)houses.growthPeriod=growthLabel;if(units)units.growthPeriod=growthLabel;
  return {name:profileName.trim(),postcode:parsed.postcode,state:parsed.state,region:`${parsed.state} suburb profile`,url,updated:`Data refreshed ${refresh}`,houses:completeLocal(houses)?houses:null,units:completeLocal(units)?units:null,priceHistory,sourceName:'Heatmaps.com.au',mode:'Live suburb profile'};
}
function parseViewBlock(block){
  if(!block)return null;const out={median:null,annualGrowth:null,rent:null,yield:null,sold:null,days:null,stockPct:null,listings:null,totalStock:null};let m;
  m=block.match(/\$([0-9,.]+[mk]?)\s+Median sale price/i);if(m)out.median=moneyNum(m[1]);
  m=block.match(/([+\-−]?[0-9.]+)%\s+Past 12 month growth/i);if(m){out.annualGrowth=num(m[1]);out.growthPeriod='Past 12 months';}
  m=block.match(/([0-9.]+)%\s+Rental yield/i);if(m)out.yield=num(m[1]);
  m=block.match(/([0-9,]+)\s+Properties sold/i);if(m)out.sold=num(m[1]);
  m=block.match(/([0-9,]+)\s+days\s+Average days on market/i);if(m)out.days=num(m[1]);
  return out;
}
function parseView(text,parsed,url){
  const houses=parseViewBlock(section(text,'House trends','Apartment & Unit trends'));const units=parseViewBlock(section(text,'Apartment & Unit trends','Properties For Sale'));
  if(![houses,units].some(completeLocal))return null;
  return {name:parsed.name,postcode:parsed.postcode,state:parsed.state,region:`${parsed.state} suburb profile`,url,updated:'Latest available',houses:completeLocal(houses)?houses:null,units:completeLocal(units)?units:null,sourceName:'view.com.au',mode:'Live suburb profile'};
}
function parseReaMetricBlock(block,plural){
  if(!block)return null;let m;const out={median:null,annualGrowth:null,listings:null,sold:null,days:null,buyers:null,rent:null,yield:null,stockPct:null,totalStock:null};
  m=block.match(/Median price\s*\$([0-9,]+)/i);if(m)out.median=num(m[1]);m=block.match(/Past 12 month growth\s*Up\s*([0-9.]+)%/i);if(m){out.annualGrowth=num(m[1]);out.growthPeriod='Past 12 months';}else if((m=block.match(/Past 12 month growth\s*Down\s*-?([0-9.]+)%/i))){out.annualGrowth=-num(m[1]);out.growthPeriod='Past 12 months';}m=block.match(new RegExp(`([0-9,]+) ${plural} available in the past month`,'i'));if(m)out.listings=num(m[1]);m=block.match(/([0-9,]+) sold(?: sold)? in the past 12 months/i);if(m)out.sold=num(m[1]);m=block.match(/([0-9,]+) days median days on market/i);if(m)out.days=num(m[1]);m=block.match(/([0-9,]+) buyers interested/i);if(m)out.buyers=num(m[1]);m=block.match(/([0-9.]+)% rental yield/i);if(m)out.yield=num(m[1]);return out;
}
function parseReaRental(block){const m=block?.match(/Median rental price\s*\$([0-9,]+)/i);return m?num(m[1]):null;}
function parseRea(text,parsed,url){
  const houseBuy=section(text,'Median price snapshot for houses','Median rental price snapshot for houses')||section(text,'Median price snapshot for houses','Unit and apartment price guide');const houseRent=section(text,'Median rental price snapshot for houses','Unit and apartment price guide');const unitBuy=section(text,'Median price snapshot for units','Median rental price snapshot for units');const unitRent=section(text,'Median rental price snapshot for units','Median price snapshot This table');const houses=parseReaMetricBlock(houseBuy,'houses'),units=parseReaMetricBlock(unitBuy,'units');if(houses)houses.rent=parseReaRental(houseRent);if(units)units.rent=parseReaRental(unitRent);if(![houses,units].some(completeLocal))return null;const period=(houseBuy.match(/(January|February|March|April|May|June|July|August|September|October|November|December)\s+20\d{2}\s*-\s*(January|February|March|April|May|June|July|August|September|October|November|December)\s+20\d{2}/i)||[])[0]||'Latest 12 months';return{name:parsed.name,postcode:parsed.postcode,state:parsed.state,region:`${parsed.state} suburb profile`,url,updated:period,houses:completeLocal(houses)?houses:null,units:completeLocal(units)?units:null,sourceName:'realestate.com.au',mode:'Live suburb profile'};
}

const VERIFIED_SUBURB_FALLBACKS={
  'NSW-2488-BOGANGAR':{
    name:'Bogangar',postcode:'2488',state:'NSW',region:'Cabarita Beach Region, NSW',
    url:'https://www.realestate.com.au/nsw/bogangar-2488/',updated:'September 2025 – August 2026',
    houses:{median:1770000,annualGrowth:11.3,rent:1200,yield:3.4,sold:36,days:55,stockPct:null,listings:12,totalStock:null,growthPeriod:'Past 12 months'},
    units:{median:1060000,annualGrowth:-4.5,rent:863,yield:4.0,sold:39,days:38,stockPct:null,listings:5,totalStock:null,growthPeriod:'Past 12 months'},
    priceHistory:null,sourceName:'realestate.com.au',mode:'Verified source fallback',verifiedFallback:true
  }
};
function verifiedSuburbFallback(parsed){
  const key=`${parsed.state}-${parsed.postcode}-${normaliseSuburbName(parsed.name)}`;
  const f=VERIFIED_SUBURB_FALLBACKS[key]; return f?{...f,fetchedAt:new Date().toISOString()}:null;
}

async function buildSuburb(query){
  const resolution=await resolveSuburbQuery(query);
  if(resolution.error)return resolution;
  if(resolution.needsChoice)return resolution;
  const parsed=resolution.parsed;const slug=slugify(parsed.name),state=parsed.state.toLowerCase();
  const candidates=[
    {name:'Heatmaps.com.au',url:`https://heatmaps.com.au/suburbs/${state}/${slug}-${parsed.postcode}/`,parse:parseHeatmaps},
    {name:'view.com.au',url:`https://view.com.au/${state}/${slug}-${parsed.postcode}/`,parse:parseView},
    {name:'realestate.com.au',url:`https://www.realestate.com.au/${state}/${slug}-${parsed.postcode}/`,parse:parseRea}
  ];
  const failures=[];
  for(const c of candidates){try{const html=await fetchText(c.url,9000);const out=c.parse(textify(html),parsed,c.url);if(out)return {...out,fetchedAt:new Date().toISOString()};failures.push(`${c.name}: data not recognised`)}catch(e){failures.push(`${c.name}: unavailable`)}}
  const verified=verifiedSuburbFallback(parsed); if(verified)return verified;
  return {error:'The suburb exists, but its current market profile could not be read from the available sources right now. Try again shortly or choose another suggestion.',status:404,attempts:failures,resolved:parsed};
}

function calculateLocalPulse(profile){
  const types=[profile?.houses,profile?.units].filter(Boolean); if(!types.length)return {score:0,category:'Extreme Fear',coverage:0};
  const weighted=(field,weightField='sold')=>{
    const valid=types.filter(x=>Number.isFinite(x?.[field])); if(!valid.length)return null;
    const total=valid.reduce((sum,x)=>sum+(Number.isFinite(x?.[weightField])&&x[weightField]>0?x[weightField]:1),0);
    return valid.reduce((sum,x)=>sum+x[field]*(Number.isFinite(x?.[weightField])&&x[weightField]>0?x[weightField]:1),0)/total;
  };
  const growth=weighted('annualGrowth'), days=weighted('days');
  let stockPct=null; const stockTypes=types.filter(x=>Number.isFinite(x?.stockPct));
  if(stockTypes.length){
    const withStock=stockTypes.filter(x=>Number.isFinite(x?.totalStock)&&x.totalStock>0);
    if(withStock.length){const total=withStock.reduce((sum,x)=>sum+x.totalStock,0);stockPct=withStock.reduce((sum,x)=>sum+x.stockPct*x.totalStock,0)/total;}
    else stockPct=stockTypes.reduce((sum,x)=>sum+x.stockPct,0)/stockTypes.length;
  }
  const parts=[];
  if(Number.isFinite(growth))parts.push({weight:.4,score:linear(growth,-10,15)});
  if(Number.isFinite(days))parts.push({weight:.3,score:linear(-days,-90,-20)});
  if(Number.isFinite(stockPct))parts.push({weight:.3,score:linear(-stockPct,-2.5,-.2)});
  const coverage=parts.reduce((sum,x)=>sum+x.weight,0);
  const score=coverage?Math.round(parts.reduce((sum,x)=>sum+x.score*x.weight,0)/coverage):0;
  return {score,category:categoryFor(score),coverage:Math.round(coverage*100)};
}
async function readBlobJson(path){
  try{
    const {get}=await import('@vercel/blob'); const result=await get(path,{access:'private',useCache:false});
    if(!result||result.statusCode!==200)return [];
    const txt=await new Response(result.stream).text(); try{return JSON.parse(txt);}catch{return [];}
  }catch{return null;}
}
async function writeBlobJson(path,data){
  const {put}=await import('@vercel/blob');
  await put(path,JSON.stringify(data),{access:'private',allowOverwrite:true,contentType:'application/json'});
}
async function maybeSaveSuburbHistory(profile){
  const pulse=calculateLocalPulse(profile); const key=`${profile.state}-${profile.postcode}-${slugify(profile.name)}`.toLowerCase();
  const path=`property-pulse/suburbs/${key}.json`; let history=await readBlobJson(path); if(!Array.isArray(history))history=[];
  const updatedAt=profile.fetchedAt||new Date().toISOString(), day=updatedAt.slice(0,10);
  const entry={id:crypto.randomUUID(),date:day,updatedAt,score:pulse.score,category:pulse.category,coverage:pulse.coverage,houseMedian:Number.isFinite(profile?.houses?.median)?profile.houses.median:null,unitMedian:Number.isFinite(profile?.units?.median)?profile.units.median:null,sourceUpdated:profile.updated||null,sourceName:profile.sourceName||null};
  const idx=history.findIndex(x=>x.date===day); if(idx>=0)history[idx]=entry; else history.push(entry);
  history=history.sort((a,b)=>a.date.localeCompare(b.date)).slice(-365);
  await writeBlobJson(path,history); return {ready:true,key,pulse,history};
}
async function readCloudHistory(){
  try{
    const {get}=await import('@vercel/blob');
    const result=await get('property-pulse/history.json',{access:'private',useCache:false});
    if(!result||result.statusCode!==200)return [];
    const txt=await new Response(result.stream).text();
    try{return JSON.parse(txt);}catch{return [];}
  }catch{return null;}
}
async function writeCloudHistory(history){
  const {put}=await import('@vercel/blob');
  await put('property-pulse/history.json',JSON.stringify(history),{access:'private',allowOverwrite:true,contentType:'application/json'});
}
async function maybeSaveHistory(payload){
  let history=await readCloudHistory(); if(!Array.isArray(history))history=[];
  const day=payload.updatedAt.slice(0,10); const cityHistory=Object.fromEntries(Object.entries(payload.cities||{}).map(([k,c])=>[k,{score:c.score,category:c.category,coverage:c.coverage,priceMomentum3m:c.priceMomentum3m,auctionClearance:c.auctionClearance}])); const entry={id:crypto.randomUUID(),date:day,updatedAt:payload.updatedAt,score:payload.national.score,category:payload.national.category,inputs:payload.inputs,cities:cityHistory};
  const idx=history.findIndex(x=>x.date===day); if(idx>=0)history[idx]=entry; else history.push(entry);
  history=history.sort((a,b)=>a.date.localeCompare(b.date)).slice(-180); await writeCloudHistory(history); return {ready:true,saved:true,count:history.length};
}

function json(res,status,body){res.statusCode=status;res.setHeader('Content-Type','application/json; charset=utf-8');res.setHeader('Cache-Control','no-store');res.end(JSON.stringify(body));}

export default async function handler(req,res){
  try{
    const u=new URL(req.url,'https://property-pulse-au.vercel.app'); const action=u.searchParams.get('action')||'market';
    if(action==='market')return json(res,200,await buildMarket());
    if(action==='rates')return json(res,200,await buildRates());
    if(action==='media'){const raw=u.searchParams.get('propertyScore'),ps=raw===null?NaN:Number(raw);return json(res,200,await buildMedia(Number.isFinite(ps)&&ps>=0&&ps<=100?ps:null));}
    if(action==='suggest')return json(res,200,{suggestions:await suggestSuburbs(u.searchParams.get('query'))});
    if(action==='suburb'){
      const out=await buildSuburb(u.searchParams.get('query')); if(out.error)return json(res,out.status||400,out); if(out.needsChoice)return json(res,200,out);
      const saved=await maybeSaveSuburbHistory(out).catch(()=>null);
      return json(res,200,{...out,pulse:saved?.pulse||calculateLocalPulse(out),suburbHistory:saved?.history||[],suburbCloudReady:Boolean(saved?.ready)});
    }
    if(action==='history'){
      const h=await readCloudHistory(); return json(res,200,{cloudReady:h!==null,history:h||[]});
    }
    if(action==='health')return json(res,200,{ok:true,version:'0.4.3',cloudReady:Boolean(process.env.BLOB_READ_WRITE_TOKEN||process.env.BLOB_STORE_ID||process.env.VERCEL_OIDC_TOKEN),time:new Date().toISOString()});
    return json(res,404,{error:'Unknown action'});
  }catch(e){console.error(e);return json(res,500,{error:'Property Pulse API error',detail:String(e?.message||e)});}
}
