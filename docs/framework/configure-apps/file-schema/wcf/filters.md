---
title: '&lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: 5f50b1ad4abfa77022a17d6497b614721382ec1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600193"
---
# <a name="ltfiltersgt"></a><span data-ttu-id="7a0d7-102">&lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="7a0d7-102">&lt;filters&gt;</span></span>

<span data-ttu-id="7a0d7-103">L'elemento `filters` contiene una raccolta dei filtri di XPath usati per controllare che tipo di messaggi viene registrato.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="7a0d7-104">I filtri vengono applicati solo al livello di trasporto, specificato da `logMessagesAtTransportLevel` impostato `true`.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="7a0d7-105">I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="7a0d7-106">Per aggiungere un filtro alla raccolta, usare la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="7a0d7-107">Quando sono definiti uno o più filtri, solo i messaggi che corrispondono almeno a uno dei filtri vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="7a0d7-108">Se non è definito alcun filtro, passeranno tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="7a0d7-109">I filtri supportano la sintassi Xpath completa e sono applicati nell'ordine in cui vengono visualizzati nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="7a0d7-110">Un filtro sintatticamente errato determina un'eccezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="7a0d7-111">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="7a0d7-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a0d7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a0d7-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="7a0d7-113">Configurazione della registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="7a0d7-113">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="7a0d7-114">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="7a0d7-114">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
