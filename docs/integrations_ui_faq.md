---
layout: default
title: FAQs for Embeddable BI dashboards
parent: Links to analytical dashboards
grand_parent: Integrations
has_children: false
has_toc: false
nav_order: 1
---

## Frequently asked questions

### 1. How is this concept different from Matrix Command Centre ?

#### 1.1. Command Centre
[Matrix Command Centre](/integrations_cc.html) provides a single long-lived dashboard within Matrix web platform.

1. You can access this module using the Command Centre icon in the SmartClean Matrix web platform.
   1. Therefore, you need to sign-in to the Matrix web platform first.
   
2. Command Centre provides useful information (analytics) from other relevant modules in one place
   1. Accessible within the standard web platform
   2. For example, the following widgets are included in the original (pre-configured) Command Centre: 
      1. Recent activity (such as updates to Incidents)
      2. Summary of solutions (such as usage monitoring)
      3. Audit activities
      4. TaskBoard
   
3. Set of widgets available on activation are different from those available by default in an Embeddable BI dashboard.

4. This web page needs to be refreshed to load it with new data.

#### 1.2. Embeddable BI Dashboards

[Embeddable BI](/integrations_ui.html) provides links to short-lived, customisable dashboards on request.

1. This service is meant for integrations
   1. For example - to view or embed live dashboards in your own application or platform.
   2. Activate the API by contacting us:
      1. Please open a support ticket with us, or 
      2. Contact your SmartClean account manager.

2. Enable automatic refresh using an icon at bottom of the dashboard
   1. Can be set to a desired interval: (1 / 5 / 10 / 15 / 30 / 60 minutes) 
   2. This is disabled by default when the link is first opened.

   
### 2. How secure are these dashboards and associated links ?
Apart from few controls for visualization, there are no inputs on the dashboard for any custom data

#### 2.1. Encrypted website
Links to open **these dashboards always open on to an encrypted website**.

1. These links are generated in a trusted web domain:
   1. Each link starts with `https://realsense.metabaseapp.com/embed/dashboard`
      1. "_realsense_" comes from the SmartClean RealSense vertical
      2. "_metabaseapp_" comes from our BI service partner: [Metabase](https://www.metabase.com)
2. The website uses a signed digital certificate for encryption.
   1. Issued by a legitimate, standard Certificate Authority: [Lets Encrypt](https://letsencrypt.org)
3. Automatic renewal of certificate happens during expiry time. 
   1. This is set-up via the [CertBot Tool](https://certbot.eff.org).
4. To see more details about the digital certificate and check the validity:
   1. Click on the lock icon next to the website on your browser.

#### 2.2. Protected from manipulation
Any manipulation at any level will lead to a failure to load the dashboard.

1. Request to generate links to these dashboards **require authentication**.
   1. The request will only succeed if the authentication check passes.
   2. A user session is created for the same.
2. Each **link is specific to an authenticated session** for the user account. 
   1. These also count towards the user sessions quota in your SmartClean account.
3. Value of "URI" in the response is base-64 encoded form of the desired URL. 
4. After decoding this value the URL is composed of the following parts:
   1. Domain and service identifier: `https://realsense.metabaseapp.com/embed/dashboard/`
   2. JWT authentication token following the above part
      1. This contains the signature and certain attributes from the request.
      2. Any manipulation (such as getting URL by updating attributes in the JWT) is detected by the signature matching algorithm.
