---
layout: default-layout
title: Dynamsoft Licensing FAQ
keywords: Barcode reader, licensing
description: This page lists the frequently asked questions about Dynamsoft's Dynamsoft License Server.
breadcrumbText: Licensing FAQ
needAutoGenerateSidebar: true
hasCustomLdJson: true
noTitleIndex: true
customLdJsonScript: 
---
<script type="application/ld+json">
{
  "@context": "https://schema.org", 
  "@type": "FAQPage", 
  "mainEntity": [{

    "@type": "Question",
    "name": "Does license tracking disclose any private information?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "No, the license tracking process does not disclose any private information. For licensing purposes, Dynamsoft SDKs that use online licensing will keep track of the actual usage locally (for example, the symbology types and number of scans for Dynamsoft Barcode Reader), then the usage information is condensed into a report and sent to the Dynamsoft License Server ( DLS ) every 3 minutes. Once submitted, the records are purged on the local machine. Note that the report is all about usage of certain features and nothing about the actual output of these operations."

    }

  }, {

    "@type": "Question",
    "name": "How secure is the Dynamsoft License Server?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "The Dynamsoft License Server ( DLS ) is the only software that Dynamsoft SDKs would be communicating with at runtime, so the security of DLS matters."

    }

  }, {

    "@type": "Question",
    "name": "Can a client device work offline?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "Yes. Depending on the license type, once a client device gets authorized, it can be used offline for 3 ~ 365 days. After that, it must connect to DLS again for another authorization. Otherwise, it will stop working.

During the offline period, by default, all usage data is kept on the client side and will be sent to the DLS all at once the next time the device gets online."

    }

  }, {

    "@type": "Question",
    "name": "Can I use Dynamsoft SDKs in an environment with no internet connection?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "Yes. There are two scenarios in this case.

All client devices can connect to a local network within the organization. In this case, you can simply host your own DLS for license tracking. Please see Self-hosted License Tracking.
Client devices never connect to any network. In this case, you may require a special license. Please contact Dynamsoft Support Team for details."

    }

  }, {

    "@type": "Question", 
    "name": "Can I unregister inactive devices?", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "As mentioned in Per Device license, Dynamsoft keeps a list of UUIDs which identify the active devices. By default, only if a device hasn’t been used for over 365 days will its UUID be removed from the list. This is done automatically."

    }

  }, {

    "@type": "Question",
    "name": "Can I extend the quota of my license to support more devices or process more documents?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "Yes. If you are using Dynamsoft-Hosted DLS, you can either contact sales@dynamsoft.com to add quota or log in the customer portal and place an order for extra quota yourself. Rest assured that the license key remains unchanged during the process, so no code change is required to your application once the quota is added.

If you are hosting your own DLS, all you need to do is purchase another license, import it in the DLS and configure it to the license key you have been using."

    }

  }, {

    "@type": "Question", 
    "name": "Can I renew my license before its current expiration date?", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "Yes, you can log into the customer portal to renew your license by credit card or PayPal any time before it expires. Alternatively, you can contact sales@dynamsoft.com if you prefer other payment methods (wire transfer or check)."

    }

  }, {

    "@type": "Question", 
    "name": "Can I purchase a license valid for more than one year?", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "Yes. Please contact sales@dynamsoft.com with your request."

    }

  }, {

    "@type": "Question", 
    "name": "Will the unused quota be rolled over to the next period?", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "No."

    }

  }, {

    "@type": "Question", 
    "name": "What is counted as a single application?", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "Definition of a single application >"

    }

  }, {

    "@type": "Question", 
    "name": "Policies", 
    "acceptedAnswer": {
      "@type": "Answer", 
      "text": "Learn more about our policies ›"

    }

  }]
}
</script>

# Dynamsoft License Server FAQ

Table of Contents

* [What are the differences between online and offline licenses](#what-are-the-differences-between-online-and-offline-licenses)?
* [Does online licenses disclose any private information](#does-online-licenses-disclose-any-private-information)?
* [How secure is Dynamsoft License Server](#how-secure-is-dynamsoft-license-server)?
* [How reliable is the License Server hosted by Dynamsoft](#how-reliable-is-the-license-server-hosted-by-dynamsoft)?
* [How can I protect my online license](#how-can-i-protect-my-online-license)?
* [What happens if my license runs out](#what-happens-if-my-license-runs-out)?
* [Can a client device work offline](#can-a-client-device-work-offline)?
* [Can I use Dynamsoft SDKs in an environment with no internet connection](#can-i-use-dynamsoft-sdks-in-an-environment-with-no-internet-connection)?
* [Can I unregister inactive devices](#can-i-unregister-inactive-devices)?
* [Can I extend the quota of my license to support more devices or process more documents](#can-i-extend-the-quota-of-my-license-to-support-more-devices-or-process-more-documents)?
* [Can I renew my license before its current expiration date](#can-i-renew-my-license-before-its-current-expiration-date)?
* [Can I purchase a license valid for more than one year](#can-i-purchase-a-license-valid-for-more-than-one-year)?
* [Will the unused quota be rolled over to the next period](#will-the-unused-quota-be-rolled-over-to-the-next-period)?
* [What is counted as a single application](#what-is-counted-as-a-single-application)?
* [Policies](#policies)

## What are the differences between online and offline licenses?

An online license is a license that a client needs to acquire from Dynamsoft License Server (DLS) at runtime. On the contrary, an offline license is one that the client can use on its own. In other words, the license key for an online license contains only information on how to connect to DLS to acquire the actual license content while an offline license is the license content itself.

## Does online licenses disclose any private information?

No, online licenses does not disclose any private information.

* About the license usage

For licensing purposes, Dynamsoft SDKs that use online licenses will keep track of the actual usage locally (for example, the symbology types and number of scans for Dynamsoft Barcode Reader or the number of images acquired by Dynamic Web TWAIN), then the usage information is condensed into a report and sent to DLS every 3 minutes. Once submitted, the records are purged on the local machine. Note that the report is all about usage of certain features and nothing about the actual output of these operations.

* About device identification

To uniquely identify a device, an UUID is generated per device that is cached locally and included in all communications with DLS. This UUID is encoded with a random string and there is no way to tell any private information about this device.

Apart from the license usage and the UUID, DLS collects nothing else. In other words, DLS does not know anything about the user or device except that it is using Dynamsoft SDKs.

A few things to note

* DLS can either be the official one provided by Dynamsoft or one that’s hosted by yourself.
* If you don't want to share any information with Dynamsoft, you can contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) to get an offline license.

## How secure is Dynamsoft License Server?

DLS is the only software that Dynamsoft SDKs would be communicating with at runtime, so the security of DLS matters. The following are the security features of DLS :

* DLS supports HTTPS and it is highly recommended that it runs via HTTPS.
* DLS supports application binding. With application binding, authorization to use the SDK is only granted to requests sent from the application that has its ID, name or domain bound.
* DLS supports setting a session password to avoid abuse.
* DLS is responsible for authorizing the SDKs as well as tracking the usage. It is designed to send/receive static data only when requested. No script can be run remotely on DLS nor from DLS to the requesting clients.
* Authorizations sent back by DLS and usage reports sent to DLS are specially encrypted and cannot be deciphered by any other party.

Last but not least, Dynamsoft is [ISO 27001](https://www.iso.org/isoiec-27001-information-security.html) certified and we take information & data security seriously.

## How reliable is the License Server hosted by Dynamsoft?

Customer devices rely on the License Server to get authorizations for using Dynamsoft SDKs, therefore, its reliability is crucial. The following are the measures we have in place for maximum uptime:

* DLS is hosted on AWS.
* DLS database is backed up every 60 minutes.
* There are always two instances of "DLS" running in parallel on different machines with their databases synchronized every 10 minutes. If one of them fails, the other will step up to take over all incoming requests.
* Once a device is authorized, it can work offline for a period of time (from 3 minutes to a maximum of 365 days or more, depending on the license type).
* Dynamsoft server administrators are notified within 30 seconds of any server exceptions.

Also, Dynamsoft has been an online service provider for over 13 years and has an experienced team who have been maintaining products like SourceAnywhere Hosted, SCMAnywhere Hosted, TFS Hosted, etc.

## How can I protect my online license?

To protect your online license, we recommend you take the following measures:

* Set a [session password]({{site.about}}terms.html#session-password). The license only works when the license key you use in your application contains the same session password you set for the license on DLS. If it's not too much trouble, you can update this password every time you update your app.

* Set a [validation field]({{site.about}}terms.html#valication-field). A validation field (also called binding information) is a static characteristic of the application (e.g. the domain of a web application, the process name of a desktop application, etc.). Dynamsoft SDKs will collect this information at runtime and include it in the requests sent to DLS. This way, you can limit license usage to your application.

## What happens if my license runs out?

Generally, each online license has a fixed quota. If the quota is exhausted, the license will no longer be valid and the software will stop functioning, which is unacceptable for a production environment. To make sure it doesn't happen accidentally, Dynamsoft has the following measures:

* Dynamsoft allows excessive usage of the licenses in case the licensee fails to extend or expand the license in time. Contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) for more information.

* Dynamsoft notifies the licensee multiple times about the status of the license. See [Usage Alerts]({{site.common}}usagealerts.html) for more information.

## Can a client device work offline?

Yes. Depending on the license type, once a client device gets authorized, it can be used offline for a period of time (from 3 minutes to a maximum of 365 days or more).

During offline, all usage data is saved on the client by default and sent to DLS in one go the next time the device goes online.

Contact [Dynamsoft Support Team](mailto:support@dynamsoft.com) if you would like your devices to work offline for a longer period of time. You can also contact us if you don't want to share any usage data with Dynamsoft.

## Can I use Dynamsoft SDKs in an environment with no internet connection?

Yes. There are two scenarios in this case

* All client devices can connect to a local network within the organization.

  In this case, you can simply host your own DLS. See [Self-hosted License Tracking]({{site.selfhosted}}index.html) for more information.

* Client devices never connect to any network.

  In this case, you may require a special license. Contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) for more information.

## Can I unregister inactive devices?

As mentioned in [Per Device license]({{site.about}}licensetypes.html#per-client-device), DLS keeps a list of UUIDs which identify the active devices. By default, a device is only unregistered (removed from the list) after it expires. For example, a device is unregistered if it stays offline or idle for more than 90 days for a Quaterly active license.

If your business/user turnover is high, you can choose to use a Daily Active license or even a [Concurrent Device license]({{site.about}}licensetypes.html#per-concurrent-device).

## Can I extend the quota of my license to support more devices or process more documents?

Yes. You can either contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) to add quota or log in the [customer portal](https://www.dynamsoft.com/customer/license/fullLicense) and place an order for extra quota yourself.

If you are hosting your own DLS , all you need to do is purchase another license, import it in the DLS and configure it to the same project (the same license key).

## Can I renew my license before its current expiration date?

Yes, you can log into the [customer portal](https://www.dynamsoft.com/customer/license/fullLicense) to renew your license by credit card or PayPal any time before it expires. Alternatively, you can contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) if you prefer other payment methods (wire transfer or check, etc.).

If you are using Dynamsoft's License Servers , the new license will be automatically configured to the same project (the same license key) that you have been using, so no code change is required to your application.

If you are hosting your own DLS , you need to download the new license file after the renewal, import it in DLS and configure it to the project you have been using.

## Can I purchase a license valid for more than one year?

Yes. Please contact [Dynamsoft Sales](mailto:sales@dynamsoft.com) with your request.

## Will the unused quota be rolled over to the next period?

No.

## What is counted as a single application?

[Definition of a single application >](https://www.dynamsoft.com/Products/single-application.aspx)

## Policies

[Learn more about our policies ›](https://www.dynamsoft.com/Products/policies.aspx)
