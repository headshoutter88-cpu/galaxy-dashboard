# galaxy-dashboard
Galaxy Toy Enterprise - Professional Dashboard with Firebase, Google Ads &amp; Analytics Integration
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- AdSense & SEO -->
<meta name="google-adsense-account" content="ca-pub-1529705675308771">
<meta name="description" content="Galaxy Toy Enterprise - International Shopping and Tech Hub">
<title>Galaxy Toy Hub | @HeaD_ShoutteR</title>

<!-- Typography -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,600,700&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<!-- Google Tag Manager / Ads -->
<script async src="https://www.googletagmanager.com/gtag/js?id=AW-16755347386"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'AW-16755347386');
</script>

<style>
/* Core Styling - Logic & Visual Engine */
:root {
    --primary-blue: #1a73e8;
    --success-green: #34a853;
    --dark-bg: #202124;
    --bg: #f1f3f4;
}

body { font-family: 'Open Sans', sans-serif; background: var(--bg); margin: 0; color: #202124; }
.main-header { background: var(--dark-bg); color: white; padding: 40px 20px; text-align: center; }
.main-header h1 { margin: 0; font-size: 2.2rem; }
.status-chip { background: var(--primary-blue); display: inline-block; padding: 5px 15px; border-radius: 15px; font-size: 0.85rem; margin-top: 10px; }

.container { max-width: 1000px; margin: 20px auto; padding: 0 20px; }
.card { background: white; margin: 20px 0; padding: 25px; border-radius: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.12); }
.card h2 { color: var(--primary-blue); border-bottom: 2px solid var(--success-green); padding-bottom: 10px; }
.success-text { color: var(--success-green); font-weight: 700; }

.action-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin-top: 20px; }
.btn { 
    display: block; background: var(--primary-blue); color: white; text-decoration: none; 
    padding: 12px; border-radius: 4px; text-align: center; font-weight: 600; transition: 0.3s;
    border: none; cursor: pointer; font-size: 1rem;
}
.btn:hover { background: #1557b0; transform: translateY(-2px); }
.btn.green { background: var(--success-green); }
.btn.green:hover { background: #2d8e47; }

footer { text-align: center; padding: 20px; color: #5f6368; font-size: 0.9rem; }
.log-box { background: #202124; color: #34a853; padding: 15px; border-radius: 5px; font-family: 'Courier New'; font-size: 0.85rem; max-height: 200px; overflow-y: auto; }
</style>
</head>
<body>
<header class="main-header">
    <h1><i class="fa-solid fa-rocket"></i> Galaxy Toy 🇧🇩</h1>
    <div class="status-chip">Merchant ID: BCR2DN4TUOY25CCD</div>
</header>

<main class="container">
    <!-- Layer 1: Entry Architecture -->
    <section class="card">
        <h2>System Verification</h2>
        <p class="success-text"><i class="fa-solid fa-circle-check"></i> Success... Hooray! All systems operational.</p>
        <p>Project: <b>fairbase-project-75908</b> | AdSense: <b>ca-pub-1529705675308771</b></p>
    </section>

    <!-- Layer 2: Logic & SDK Engine -->
    <section class="card">
        <h2>SDK & Automation Controls</h2>
        <div class="action-grid">
            <button class="btn" onclick="trackWithdrawals()"><i class="fa-solid fa-coins"></i> Check TON Withdrawals</button>
            <button class="btn" onclick="requestChromePermission()"><i class="fa-brands fa-chrome"></i> Request Chrome Access</button>
            <button class="btn green" onclick="exportCSV()"><i class="fa-solid fa-file-csv"></i> Export Product CSV</button>
            <a href="https://pay.google.com/business/console/home/BCR2DN4TUOY25CCD" target="_blank" class="btn"><i class="fa-solid fa-credit-card"></i> Payment Console</a>
        </div>
        <h3 style="margin-top:20px">System Log:</h3>
        <div id="logOutput" class="log-box">System Initialized...</div>
    </section>

    <!-- Layer 3: Data Blueprint -->
    <section class="card">
        <h2>Resource Links</h2>
        <div class="action-grid">
            <a href="https://toybd2023.blogspot.com" target="_blank" class="btn">View Blog</a>
            <a href="https://galaxytoyenterprise.blogspot.com" target="_blank" class="btn">Enterprise Blog</a>
            <a href="https://adsense.google.com/adsense/u/0/pub-1529705675308771/onboarding" target="_blank" class="btn">AdSense Console</a>
            <a href="https://console.cloud.google.com/monitoring/dashboards?project=galaxy-toy-enterprise" target="_blank" class="btn">Cloud Monitoring</a>
        </div>
    </section>
</main>

<footer>
    <p>&copy; Aug 2026 | Project: fairbase-project-75908 | Admin: alfarhabiridoy@gmail.com</p>
</footer>

<script>
// SDK Verification Listener - Layer 2: Logic Engine
const GALAXY_CONFIG = {
    projectId: "fairbase-project-75908",
    merchantId: "BCR2DN4TUOY25CCD",
    adsenseId: "ca-pub-1529705675308771"
};

function log(message) {
    const logBox = document.getElementById('logOutput');
    logBox.innerHTML += `\n> ${new Date().toLocaleTimeString()}: ${message}`;
    logBox.scrollTop = logBox.scrollHeight;
}

// Tonstakers Active Withdrawal Logic
async function trackWithdrawals() {
    log("Checking for active TON withdrawals...");
    if (window.tonstakers) {
        try {
            const withdrawals = await tonstakers.getActiveWithdrawalNFTs();
            if(withdrawals.length > 0) {
                withdrawals.forEach(nft => {
                    log(`Withdrawal of ${nft.tsTONAmount} tsTON pending.`);
                });
            } else {
                log("No active withdrawals found.");
            }
        } catch(e) { log("Error: " + e.message); }
    } else {
        log("Tonstakers SDK not detected. Please install extension.");
    }
}

// Chrome Action Permission Handler
function requestChromePermission() {
    log("Requesting Chrome permissions...");
    if (typeof chrome !== 'undefined' && chrome.action) {
        chrome.permissions.request({
            permissions: ["tabs", "scripting"],
            origins: ['https://www.google.com/']
        }, (granted) => {
            log(granted ? "Access Secured" : "Access Denied");
        });
    } else {
        log("Chrome Extension API not available. Run in Chrome Extension context.");
    }
}

// Layer 3: CSV/SDK Data Blueprint
function exportCSV() {
    log("Generating CSV for Product Catalog...");
    // Standardized CSV Export Format for Google
    const csvData = [
        ["Product ID", "Title", "Description", "Link", "Price", "Brand", "Availability"],
        ["GT-001", "Galaxy Toy Robot", "AI Powered Robot for Kids", "https://galaxytoyenterprise.blogspot.com/p/robot", "BDT 2500", "GalaxyToy", "in stock"],
        ["GT-002", "Tech Hub Controller", "Wireless Game Controller", "https://toybd2023.blogspot.com/p/controller", "BDT 1800", "GalaxyToy", "in stock"]
    ];

    let csvContent = "data:text/csv;charset=utf-8," 
        + csvData.map(e => e.join(",")).join("\n");
    
    const encodedUri = encodeURI(csvContent);
    const link = document.createElement("a");
    link.setAttribute("href", encodedUri);
    link.setAttribute("download", "galaxy_toy_product_feed.csv");
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
    log("CSV Downloaded: galaxy_toy_product_feed.csv");
}

log("Galaxy Toy Dashboard Loaded Successfully.");
console.log("Dashboard Loaded:", GALAXY_CONFIG);
</script>

</body>
</html>
