---
title: '&lt;add&gt; di &lt;filters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1ca0d5ae73d01e5bbb719f7bcc9a3f5a19fc291
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="692e3-102">&lt;add&gt; di &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="692e3-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="692e3-103">Filtro XPath che specifica il tipo di messaggio da registrare.</span><span class="sxs-lookup"><span data-stu-id="692e3-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="692e3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="692e3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="692e3-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="692e3-105">\<diagnostic></span></span>  
<span data-ttu-id="692e3-106">\<registrazione messaggi ></span><span class="sxs-lookup"><span data-stu-id="692e3-106">\<messageLogging></span></span>  
<span data-ttu-id="692e3-107">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="692e3-107">\<filters></span></span>  
<span data-ttu-id="692e3-108">\<add></span><span class="sxs-lookup"><span data-stu-id="692e3-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692e3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="692e3-109">Syntax</span></span>  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="692e3-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="692e3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="692e3-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="692e3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="692e3-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="692e3-112">Attributes</span></span>  
  
|<span data-ttu-id="692e3-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="692e3-113">Attribute</span></span>|<span data-ttu-id="692e3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="692e3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="692e3-115">filtro</span><span class="sxs-lookup"><span data-stu-id="692e3-115">filter</span></span>|<span data-ttu-id="692e3-116">Stringa che specifica una query su un documento XML definito da un'espressione di XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="692e3-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="692e3-117">Per altre informazioni, vedere <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="692e3-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="692e3-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="692e3-118">Child Elements</span></span>  
 <span data-ttu-id="692e3-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="692e3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="692e3-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="692e3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="692e3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="692e3-121">Element</span></span>|<span data-ttu-id="692e3-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="692e3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="692e3-123">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="692e3-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="692e3-124">Contiene una raccolta di filtri di XPath usati per controllare il tipo di messaggio registrato.</span><span class="sxs-lookup"><span data-stu-id="692e3-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="692e3-125">Note</span><span class="sxs-lookup"><span data-stu-id="692e3-125">Remarks</span></span>  
 <span data-ttu-id="692e3-126">I filtri vengono applicati solo al livello di trasporto, specificato da `logMessagesAtTransportLevel` impostato `true`.</span><span class="sxs-lookup"><span data-stu-id="692e3-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="692e3-127">I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="692e3-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="692e3-128">Per aggiungere un filtro alla raccolta, usare la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="692e3-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="692e3-129">Quando sono definiti uno o più filtri, solo i messaggi che corrispondono almeno a uno dei filtri vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="692e3-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="692e3-130">Se non è definito alcun filtro, passeranno tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="692e3-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="692e3-131">I filtri supportano la sintassi Xpath completa e sono applicati nell'ordine in cui vengono visualizzati nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="692e3-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="692e3-132">Un filtro sintatticamente errato determina un'eccezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="692e3-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="692e3-133">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="692e3-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="692e3-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="692e3-134">Example</span></span>  
 <span data-ttu-id="692e3-135">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="692e3-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="692e3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="692e3-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [<span data-ttu-id="692e3-137">Configurazione della registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="692e3-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="692e3-138">Configurazione della registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="692e3-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="692e3-139">\<registrazione messaggi ></span><span class="sxs-lookup"><span data-stu-id="692e3-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
