---
title: '&lt;filtri&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb8588f9699f44c584fa075e2d1e994c27f0c527
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltersgt"></a><span data-ttu-id="fdfce-102">&lt;filtri&gt;</span><span class="sxs-lookup"><span data-stu-id="fdfce-102">&lt;filters&gt;</span></span>

<span data-ttu-id="fdfce-103">L'elemento `filters` contiene una raccolta dei filtri di XPath usati per controllare che tipo di messaggi viene registrato.</span><span class="sxs-lookup"><span data-stu-id="fdfce-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="fdfce-104">I filtri vengono applicati solo al livello di trasporto, specificato da `logMessagesAtTransportLevel` impostato `true`.</span><span class="sxs-lookup"><span data-stu-id="fdfce-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="fdfce-105">I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="fdfce-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="fdfce-106">Per aggiungere un filtro alla raccolta, usare la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="fdfce-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="fdfce-107">Quando sono definiti uno o più filtri, solo i messaggi che corrispondono almeno a uno dei filtri vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="fdfce-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="fdfce-108">Se non è definito alcun filtro, passeranno tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="fdfce-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="fdfce-109">I filtri supportano la sintassi Xpath completa e sono applicati nell'ordine in cui vengono visualizzati nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fdfce-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="fdfce-110">Un filtro sintatticamente errato determina un'eccezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fdfce-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="fdfce-111">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="fdfce-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>

```xml
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">  
  <filters>  
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
      /soap:Envelope/soap:Headers  
    </add>  
  </filters>  
</messageLogging>
```

## <a name="see-also"></a><span data-ttu-id="fdfce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdfce-112">See also</span></span>

 <span data-ttu-id="fdfce-113"><xref:System.ServiceModel.Configuration.DiagnosticSection><xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [La configurazione di registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<registrazione messaggi >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="fdfce-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [\<messageLogging>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span></span>
