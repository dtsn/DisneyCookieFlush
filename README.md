# DisneyCookieFlush

This will flush the non-essential cookies from your Disney session (keeping you logged in);

*Note: I don't have the cookie issue with Disney so this might not help*

## How to use

**USE THIS AT YOUR OWN RISK**

You can use the bookmarklet (drag the link below into your bookmarks bar);

[Clear Disney Cookies](javascript: (() => {const goodCookies = [ 'PHPSESSID', 'ak_bmsc', 'Conversation_UUID', 'geolocation_aka_jar', 'geoIP_aka', 'languageSelection_jar_aka', 'AMCVS_EDA101AC512D2B230A490D4C%40AdobeOrg', 'privacy_pref', 'AMCV_EDA101AC512D2B230A490D4C%40AdobeOrg', 'localeCookie_jar_aka', 'check', 'mbox', 'akavpau_disneyworld_co_uk_profile', 'TPR-WDW-LBJS.WEB-PROD.api', 'device_747ab5b1', 'TPR-WDW-LBJS.WEB-PROD.ts', 'TPR-WDW-LBJS.WEB-PROD.token', 'TPR-WDW-LBJS.WEB-PROD-ac', 'TPR-WDW-LBJS.WEB-PROD.idn', 'SWID', 'SWID_NT', 'pep_oauth_refresh_token', 'pep_jwt_token', 'pep_oauth_token', 'authenticationSecure', 'rememberme', 'SESSION_TIMEOUT', 'SWID', 'ADRUM_BT', 'bm_sv', ]; const deleteCookie = (name) => { console.log('deleting cookie ' + name); document.cookie = name + '=' + ';path=/' + ';domain=' + window.location.hostname.replace('www.', '') + ';expires=Thu, 01 Jan 1970 00:00:01 GMT'; }; const getCookie = (name) => { return document.cookie.split(';').some((cookie) => { return cookie.trim().startsWith(name + '='); }); }; // split the cookies const arrOfCookies = document.cookie.split(';'); arrOfCookies.forEach((cookie) => { const name = cookie.split('=')[0].trim(); // if it's not a good cookie if (goodCookies.indexOf(name) === -1) { deleteCookie(name); } });})();)

## Why these cookies

These are all the cookies which are served on HTTPS so are used by the server, whereas the rest and typically non secure marketing cookies. We can probably still get rid of half of these but we need to find the ones which are causing a problem.

It may just be easier to wipe all the cookies and force you to login again.
