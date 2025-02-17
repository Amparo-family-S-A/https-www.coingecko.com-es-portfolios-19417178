# https-www.coingecko.com-es-portfolios-19417178
https://www.myetherwallet.com/wallet/nft
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <link rel="shortcut icon" href="/favicon.ico">
  <link type="application/opensearchdescription+xml" rel="search" href="/OpensearchDescription.xml"/>

  <title>Seguimiento gratuito de la cartera de criptomonedas | CoinGecko</title>
  <meta name="description" content="Realice un seguimiento de sus ganancias con más de 10.000 criptomonedas y NFT con el rastreador de cartera gratuito de CoinGecko. Ahora disponible en web y móvil." />
  
  

  <!-- OptanonConsentNoticeStart -->
<script
  src="https://cdn-apac.onetrust.com/scripttemplates/otSDKStub.js"
  data-document-language="true"
  type="text/javascript"
  charset="UTF-8"
  defer
  data-domain-script="49e8a847-f2c7-4b58-a340-caf0924064fe"
></script>
<script type="text/javascript">
  const STRICT_COOKIE = "C0001";
  const PERF_COOKIE = "C0002";
  const FUNC_COOKIE = "C0003";
  const TARGET_COOKIE = "C0004";

  const YT_DOMAIN = "www.youtube.com";
  const TW_DOMAIN = "platform.twitter.com";
  const TW_CONTAINER = "twitter-tweet";

  const CONTENT_PLACEHOLDER = "content-placeholder";

  // TODO: confirm if i18n needed
  const contentPlaceholderTemplate = `
    <div class="tw-p-6 dark:tw-bg-moon-900">
      <div class="tw-flex tw-flex-col tw-gap-4">
        <div class="tw-p-6 tw-border-solid tw-border-2 tw-border-gray-200 tw-rounded-lg dark:tw-border-moon-800">
          <div class="tw-flex">
            <div class="tw-flex-shrink-0">
              <i class="tw-text-sm fas fa-exclamation-triangle tw-text-gray-700 dark:tw-text-moon-100"></i>
            </div>
            <div class="tw-ml-3">
              <div class="tw-text-gray-700 dark:tw-text-moon-100 tw-font-semibold tw-text-base tw-leading-6 tw-flex-grow tw-mb-1">
                Couldn't load content
              </div>
              <div class="tw-font-normal tw-text-gray-500 dark:tw-text-moon-200 tw-text-base tw-leading-6 tw-flex-grow">
                This feature is currently not available because you need to provide consent to functional cookies.
                Please update your
                <span class="tw-cursor-pointer tw-font-semibold tw-underline tw-text-gray-700
                             hover:tw-text-primary-500 hover:tw-underline dark:tw-text-slate-50 dark:hover:tw-text-primary-400"
                      onclick="javascript:openPrefCenter();">Cookie Preferences</span>.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  `;

  function openPrefCenter() {
    if (window.OneTrust === undefined) { return; }

    OneTrust.ToggleInfoDisplay();
  }

  // Convenient function to extract consent values from OneTrust cookie,
  // returns an object containing category as key, true/false as value
  function getConsentCookies() {
    if (OnetrustActiveGroups === undefined) { return {}; }

    const categories = OnetrustActiveGroups.split(",").filter(c => c !== "");

    if (categories.length === 0) { return {}; }

    return categories.reduce(function (acc, cat) {
      acc[cat] = true;
      return acc;
    }, {});
  }

  // Convenient function to check if user opt-in the category,
  // pass the value from the cookie
  function optedIn(consent) {
    return !!consent;
  }

  // Convenient function to check if user opt-out the category,
  // pass the value from the cookie
  function optedOut(consent) {
    return !optedIn(consent);
  }

  // Convenient function to lookup elements by tag and
  // src/data-src domain
  function findEmbeddedElements(tag, domain) {
    const srcSelector = `${tag}[src*="${domain}"]`;
    const dataSrcSelector = `${tag}[data-src*="${domain}"]`;
    const selectors = `${srcSelector}, ${dataSrcSelector}`;
    return document.querySelectorAll(selectors);
  }

  // Convenient function to toggle between src and data-src attribute
  function toggleFrameSrc(ele, enabled) {
    const origSrc = ele.getAttribute("data-src") || ele.getAttribute("src");
    if (enabled) {
      ele.removeAttribute("data-src");
      ele.setAttribute("src", origSrc);
      ele.style.display = "block";
    } else {
      ele.removeAttribute("src");
      ele.setAttribute("data-src", origSrc);
      ele.style.display = "none";
    }
  }

  // Convenient function to toggle between script types
  function toggleScriptType(ele, enabled) {
    if (enabled) {
      ele.setAttribute("type", "text/javascript");
    } else {
      ele.setAttribute("type", "text/plain");
    }
  }

  // Convenient function to toggle between frame display and notice display
  function toggleTagDisplay(ele, enabled) {
    ele.style.height = "auto";

    if (enabled) {
      for (let div of ele.getElementsByClassName(CONTENT_PLACEHOLDER)) {
        div.remove();
      };
    } else {
      // Prevent appending more than one placeholder
      if (ele.querySelector(`.${CONTENT_PLACEHOLDER}`) !== null) { return; }

      const contentPlaceholder = document.createElement("div");
      contentPlaceholder.classList.add(CONTENT_PLACEHOLDER);
      contentPlaceholder.innerHTML = contentPlaceholderTemplate;
      ele.appendChild(contentPlaceholder);
    }
  }

  // Detect whether there're embedded Youtube videos,
  // and change to data-src if user opt-out of cookies.
  function toggleVideoCookies(enabled) {
    const vidFrames = findEmbeddedElements("iframe", YT_DOMAIN);

    for (let vidFrame of vidFrames) {
      toggleFrameSrc(vidFrame, enabled);
      const vidContainer = vidFrame.parentElement;
      toggleTagDisplay(vidContainer, enabled);
    }
  }

  // Detect whether there're embedded Twitter/X posts,
  // and change to data-src if user opt-out of cookies.
  function toggleTwitterCookies(enabled) {
    // Embedded Twitter posts
    const tweetFrames = findEmbeddedElements("iframe", TW_DOMAIN);

    for (let tweetFrame of tweetFrames) {
      toggleFrameSrc(tweetFrame, enabled);
      const tweetContainer = tweetFrame.parentElement;
      // Only post iframe has a container parent
      if (tweetContainer.classList.contains(TW_CONTAINER)) {
        toggleTagDisplay(tweetContainer, enabled);
      }
    }

    // Twitter JS script
    const tweetScript = findEmbeddedElements("script", TW_DOMAIN)[0];
    if (tweetScript !== undefined) {
      toggleScriptType(tweetScript, enabled);
    }
  }

  // remove all targeted ad local storage
  function removeTargetingAdLocalStorage(enabled) {
    if (!enabled) {
      localStorage.removeItem("adTargetingCoins");
      localStorage.removeItem("adTargetingCategories");
      localStorage.removeItem("adTargetingChains");
      localStorage.removeItem("adTargetingDeveloper");
    }
  }

  function sendPerformanceCookieChanged(enabled) {
    window.dispatchEvent(
      new CustomEvent("coingecko-performance-cookie-consent-changed", {
        detail: {
          enabled: enabled,
        }
      })
    );
  }
  
  // TODO:
  // Add more logic to this function to manually block/unblock sources that set cookie,
  // eg. embedded Youtube videos, BuySellAds banner
  function toggleCookies() {
    const categories = getConsentCookies();

    toggleVideoCookies(optedIn(categories[FUNC_COOKIE]));
    toggleTwitterCookies(optedIn(categories[FUNC_COOKIE]));
    removeTargetingAdLocalStorage(optedIn(categories[TARGET_COOKIE]));
  }

  // OneTrust callback after banner SDK is loaded
  function OptanonWrapper() {
    // On first load, hide the consent banner until user scrolls,
    // subsequently do not trigger show on scroll
    if (!OneTrust.IsAlertBoxClosed()) {
      document.getElementById("onetrust-consent-sdk").style.display = "none";

      window.addEventListener("scroll", function() {
        document.getElementById("onetrust-consent-sdk").style.display = "block";
      });
    }

    document.getElementById("ot-sdk-btn").addEventListener("click", openPrefCenter);

    // On first load, always refresh consent changes accordingly
    toggleCookies();

    // OneTrust callback when user consent changes
    OneTrust.OnConsentChanged(function() {
      toggleCookies();
      sendPerformanceCookieChanged(optedIn(getConsentCookies()[PERF_COOKIE]));
    });
  }
</script>
<!-- OptanonConsentNoticeEnd -->


  <!-- START: Third-Party JS -->
  <script type="text/plain" class="optanon-category-C0002">(function (w, d, s, l, i) {
      w[l] = w[l] || [];
      w[l].push({
          'gtm.start':
              new Date().getTime(), event: 'gtm.js'
      });
      var f = d.getElementsByTagName(s)[0],
          j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : '';
      j.async = true;
      j.src =
          'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
      f.parentNode.insertBefore(j, f);
  })(window, document, 'script', 'dataLayer', 'GTM-NP34MX7');</script>
  <!-- END: Third-Party JS -->

  <!-- START: Preload Resources -->
  <link rel="preload" fetchpriority="high" as="image" href="https://static.coingecko.com/s/coingecko-logo-8903d34ce19ca4be1c81f0db30e924154750d208683fad7ae6f2ce06c76d0a56.png"/>

  <link rel="preconnect" href="//www.googletagmanager.com"/>
  <link rel="preconnect" href="https://static.coingecko.com" crossorigin="anonymous"/>
  <link rel="dns-prefetch" href="https://static.coingecko.com" crossorigin="anonymous"/>
    <script type="text/javascript" defer src="https://ads.coingecko.com/ascendeum/pub/asc.coingecko.js"></script>
    <script>
  window.googletag = window.googletag || { cmd: [] };
  const coins = JSON.parse(localStorage.getItem("adTargetingCoins"));
  const categories = JSON.parse(localStorage.getItem("adTargetingCategories"));
  const chains = JSON.parse(localStorage.getItem("adTargetingChains"));
  const developer = JSON.parse(localStorage.getItem("adTargetingDeveloper"));

  googletag.cmd.push(() => {
    googletag.pubads().setTargeting("kevelcoin", coins)
      .setTargeting("kevelchain", chains)
      .setTargeting("kevelcategories", categories)
      .setTargeting("keveldeveloper", developer);
    });
</script>

  <!-- END: Preload Resources -->

  <!-- START: SEO Tags -->
  <meta property="og:type" content="website" />
  <meta property="og:title" content="Seguimiento gratuito de la cartera de criptomonedas | CoinGecko" />
  <meta property="og:description" content="Realice un seguimiento de sus ganancias con más de 10.000 criptomonedas y NFT con el rastreador de cartera gratuito de CoinGecko. Ahora disponible en web y móvil." />
  <meta property="og:image" content="https://static.coingecko.com/s/social_image_cards/social_image_card_standard-ac72fc0532e65a63616ea57562392567892acf5998330b8bce42b41e356af961.png" />
  <meta property="og:url" content="https://www.coingecko.com/es/portfolio" />
  <meta property="og:site_name" content="CoinGecko" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:site" content="@coingecko" />
  <meta name="twitter:creator" content="@coingecko" />
  <meta name="twitter:title" content="Seguimiento gratuito de la cartera de criptomonedas | CoinGecko" />
  <meta name="twitter:description" content="Realice un seguimiento de sus ganancias con más de 10.000 criptomonedas y NFT con el rastreador de cartera gratuito de CoinGecko. Ahora disponible en web y móvil." />
  <meta name="twitter:image" content="https://static.coingecko.com/s/social_image_cards/social_image_card_standard-ac72fc0532e65a63616ea57562392567892acf5998330b8bce42b41e356af961.png" />

  <link rel="canonical" href="https://www.coingecko.com/es/portfolio" />
<link rel="alternate" hreflang="en" href="https://www.coingecko.com/en/portfolio" /><link rel="alternate" hreflang="zh" href="https://www.coingecko.com/zh/portfolio" /><link rel="alternate" hreflang="zh-tw" href="https://www.coingecko.com/zh-tw/portfolio" /><link rel="alternate" hreflang="de" href="https://www.coingecko.com/de/portfolio" /><link rel="alternate" hreflang="fr" href="https://www.coingecko.com/fr/portfolio" /><link rel="alternate" hreflang="es" href="https://www.coingecko.com/es/portfolio" /><link rel="alternate" hreflang="ja" href="https://www.coingecko.com/ja/portfolio" /><link rel="alternate" hreflang="id" href="https://www.coingecko.com/id/portfolio" /><link rel="alternate" hreflang="ru" href="https://www.coingecko.com/ru/portfolio" /><link rel="alternate" hreflang="ko" href="https://www.coingecko.com/ko/portfolio" /><link rel="alternate" hreflang="ar" href="https://www.coingecko.com/ar/portfolio" /><link rel="alternate" hreflang="th" href="https://www.coingecko.com/th/portfolio" /><link rel="alternate" hreflang="vi" href="https://www.coingecko.com/vi/portfolio" /><link rel="alternate" hreflang="it" href="https://www.coingecko.com/it/portfolio" /><link rel="alternate" hreflang="pt" href="https://www.coingecko.com/pt/portfolio" /><link rel="alternate" hreflang="pl" href="https://www.coingecko.com/pl/portfolio" /><link rel="alternate" hreflang="tr" href="https://www.coingecko.com/tr/portfolio" /><link rel="alternate" hreflang="hu" href="https://www.coingecko.com/hu/portfolio" /><link rel="alternate" hreflang="nl" href="https://www.coingecko.com/nl/portfolio" /><link rel="alternate" hreflang="ro" href="https://www.coingecko.com/ro/portfolio" /><link rel="alternate" hreflang="sv" href="https://www.coingecko.com/sv/portfolio" /><link rel="alternate" hreflang="cs" href="https://www.coingecko.com/cs/portfolio" /><link rel="alternate" hreflang="da" href="https://www.coingecko.com/da/portfolio" /><link rel="alternate" hreflang="el" href="https://www.coingecko.com/el/portfolio" /><link rel="alternate" hreflang="hi" href="https://www.coingecko.com/hi/portfolio" /><link rel="alternate" hreflang="no" href="https://www.coingecko.com/no/portfolio" /><link rel="alternate" hreflang="sk" href="https://www.coingecko.com/sk/portfolio" /><link rel="alternate" hreflang="uk" href="https://www.coingecko.com/uk/portfolio" /><link rel="alternate" hreflang="he" href="https://www.coingecko.com/he/portfolio" /><link rel="alternate" hreflang="fi" href="https://www.coingecko.com/fi/portfolio" /><link rel="alternate" hreflang="bg" href="https://www.coingecko.com/bg/portfolio" /><link rel="alternate" hreflang="hr" href="https://www.coingecko.com/hr/portfolio" /><link rel="alternate" hreflang="lt" href="https://www.coingecko.com/lt/portfolio" /><link rel="alternate" hreflang="sl" href="https://www.coingecko.com/sl/portfolio" />  <!-- END: SEO Tags -->

  <!-- START: Stylesheets -->
  <link rel="stylesheet" href="https://static.coingecko.com/packs/css/v2/application-b83dbe3d.chunk.css" />
  <link rel="preload" href="https://static.coingecko.com/s/fonts-79630041596337b4d87b9c394ce3ee53f24a117c6a4a6376b164017309067158.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="https://static.coingecko.com/s/fonts-79630041596337b4d87b9c394ce3ee53f24a117c6a4a6376b164017309067158.css"></noscript>
  <!-- END: Stylesheets -->

  <link rel="icon" type="image/png" href="/favicon-96x96.png" sizes="96x96"/>
  <link rel="icon" type="image/png" href="/favicon-32x32.png" sizes="32x32"/>
  <link rel="icon" type="image/png" href="/favicon-16x16.png" sizes="16x16"/>
  <meta name="application-name" content="CoinGecko"/>
  <meta name="action-cable-url" content="wss://cables.coingecko.com/cable" />

  

  <!-- START: Other JS Scripts -->
  <script type="text/plain" class="optanon-category-C0002" async src="https://www.googletagmanager.com/gtag/js?id=G-LJR3232ZPB"></script>
  <script type="text/plain" class="optanon-category-C0002">
      window.dataLayer = window.dataLayer || [];

      function gtag() {
          dataLayer.push(arguments);
      }

      gtag('js', new Date());
      gtag('config', 'G-LJR3232ZPB');
  </script>
  <script type="text/javascript" async src="https://btloader.com/tag?o=5172243878903808&upapi=true"></script>
  <!-- END: Other JS Scripts -->
</head>

<body data-controller="load-sentry tooltips settings login-state csrf-meta auth currency price percent-change async-percent-change application ads index-trending-coins add-coin-id-to-cookies add-nft-contract-id-to-cookies generate-uuid mixpanel-init analytics-tracker"
      data-currency-symbols="{&quot;btc&quot;:&quot;BTC&quot;,&quot;eth&quot;:&quot;ETH&quot;,&quot;ltc&quot;:&quot;LTC&quot;,&quot;bch&quot;:&quot;BCH&quot;,&quot;bnb&quot;:&quot;BNB&quot;,&quot;eos&quot;:&quot;EOS&quot;,&quot;xrp&quot;:&quot;XRP&quot;,&quot;xlm&quot;:&quot;XLM&quot;,&quot;link&quot;:&quot;LINK&quot;,&quot;dot&quot;:&quot;DOT&quot;,&quot;yfi&quot;:&quot;YFI&quot;,&quot;usd&quot;:&quot;$&quot;,&quot;aed&quot;:&quot;DH&quot;,&quot;ars&quot;:&quot;$&quot;,&quot;aud&quot;:&quot;A$&quot;,&quot;bdt&quot;:&quot;৳&quot;,&quot;bhd&quot;:&quot;BD&quot;,&quot;bmd&quot;:&quot;$&quot;,&quot;brl&quot;:&quot;R$&quot;,&quot;cad&quot;:&quot;CA$&quot;,&quot;chf&quot;:&quot;Fr.&quot;,&quot;clp&quot;:&quot;CLP$&quot;,&quot;cny&quot;:&quot;¥&quot;,&quot;czk&quot;:&quot;Kč&quot;,&quot;dkk&quot;:&quot;kr.&quot;,&quot;eur&quot;:&quot;€&quot;,&quot;gbp&quot;:&quot;£&quot;,&quot;gel&quot;:&quot;₾&quot;,&quot;hkd&quot;:&quot;HK$&quot;,&quot;huf&quot;:&quot;Ft&quot;,&quot;idr&quot;:&quot;Rp&quot;,&quot;ils&quot;:&quot;₪&quot;,&quot;inr&quot;:&quot;₹&quot;,&quot;jpy&quot;:&quot;¥&quot;,&quot;krw&quot;:&quot;₩&quot;,&quot;kwd&quot;:&quot;KD&quot;,&quot;lkr&quot;:&quot;Rs&quot;,&quot;mmk&quot;:&quot;K&quot;,&quot;mxn&quot;:&quot;MX$&quot;,&quot;myr&quot;:&quot;RM&quot;,&quot;ngn&quot;:&quot;₦&quot;,&quot;nok&quot;:&quot;kr&quot;,&quot;nzd&quot;:&quot;NZ$&quot;,&quot;php&quot;:&quot;₱&quot;,&quot;pkr&quot;:&quot;₨&quot;,&quot;pln&quot;:&quot;zł&quot;,&quot;rub&quot;:&quot;₽&quot;,&quot;sar&quot;:&quot;SR&quot;,&quot;sek&quot;:&quot;kr&quot;,&quot;sgd&quot;:&quot;S$&quot;,&quot;thb&quot;:&quot;฿&quot;,&quot;try&quot;:&quot;₺&quot;,&quot;twd&quot;:&quot;NT$&quot;,&quot;uah&quot;:&quot;₴&quot;,&quot;vef&quot;:&quot;Bs.F&quot;,&quot;vnd&quot;:&quot;₫&quot;,&quot;zar&quot;:&quot;R&quot;,&quot;xdr&quot;:&quot;XDR&quot;,&quot;xag&quot;:&quot;XAG&quot;,&quot;xau&quot;:&quot;XAU&quot;,&quot;bits&quot;:&quot;μBTC&quot;,&quot;sats&quot;:&quot;sats&quot;}"
      data-currency-override=""
      data-exchange-rate-json="{&quot;usd&quot;:&quot;96221.375&quot;,&quot;gbp&quot;:&quot;76354.932&quot;,&quot;eur&quot;:&quot;91825.886&quot;,&quot;cny&quot;:&quot;698442.095&quot;,&quot;jpy&quot;:&quot;14604876.041&quot;,&quot;cad&quot;:&quot;136526.007&quot;,&quot;rub&quot;:&quot;8809198.428&quot;,&quot;hkd&quot;:&quot;748651.467&quot;,&quot;sek&quot;:&quot;1030329.343&quot;,&quot;sgd&quot;:&quot;129034.307&quot;,&quot;krw&quot;:&quot;138829391.078&quot;,&quot;aud&quot;:&quot;151140.206&quot;,&quot;zar&quot;:&quot;1773379.861&quot;,&quot;inr&quot;:&quot;8356743.487&quot;,&quot;myr&quot;:&quot;426453.134&quot;,&quot;idr&quot;:&quot;1562042918.271&quot;,&quot;brl&quot;:&quot;548856.345&quot;,&quot;nzd&quot;:&quot;167778.902&quot;,&quot;mxn&quot;:&quot;1959226.732&quot;,&quot;php&quot;:&quot;5583534.052&quot;,&quot;dkk&quot;:&quot;684983.13&quot;,&quot;pln&quot;:&quot;382258.849&quot;,&quot;xau&quot;:&quot;33.13286831536934&quot;,&quot;xag&quot;:&quot;2965.091503535122&quot;,&quot;twd&quot;:&quot;3148439.024&quot;,&quot;xdr&quot;:&quot;73410.173&quot;,&quot;chf&quot;:&quot;86591.539&quot;,&quot;eth&quot;:&quot;35.39938189990614&quot;,&quot;aed&quot;:&quot;353419.667&quot;,&quot;ars&quot;:&quot;101633827.49&quot;,&quot;kwd&quot;:&quot;29682.562&quot;,&quot;lkr&quot;:&quot;28336037.242&quot;,&quot;sar&quot;:&quot;360872.59&quot;,&quot;try&quot;:&quot;3486156.71&quot;,&quot;thb&quot;:&quot;3244921.544&quot;,&quot;pkr&quot;:&quot;26763164.444&quot;,&quot;nok&quot;:&quot;1070059.63&quot;,&quot;ils&quot;:&quot;341967.688&quot;,&quot;huf&quot;:&quot;36933411.723&quot;,&quot;czk&quot;:&quot;2300236.922&quot;,&quot;clp&quot;:&quot;90774882.166&quot;,&quot;bdt&quot;:&quot;11649681.423&quot;,&quot;bhd&quot;:&quot;36262.853&quot;,&quot;bmd&quot;:&quot;96221
Download
# Create a folder
$ mkdir actions-runner && cd actions-runner
Copied!# Download the latest runner package
$ curl -o actions-runner-linux-x64-2.322.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.322.0/actions-runner-linux-x64-2.322.0.tar.gz
# Optional: Validate the hash
$ echo "b13b784808359f31bc79b08a191f5f83757852957dd8fe3dbfcc38202ccf5768  actions-runner-linux-x64-2.322.0.tar.gz" | shasum -a 256 -c
# Extract the installer
$ tar xzf ./actions-runner-linux-x64-2.322.0.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/Amparo-family-S-A/https-www.coingecko.com-es-portfolios-19417178 --token BO2IUSMB7SEQN7GL3BOYSBLHWMLWS
# Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted
