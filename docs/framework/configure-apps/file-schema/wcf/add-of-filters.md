---
title: <add> di <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850557"
---
# <a name="add-of-filters"></a><span data-ttu-id="951eb-102">\<add> di \<filters></span><span class="sxs-lookup"><span data-stu-id="951eb-102">\<add> of \<filters></span></span>
<span data-ttu-id="951eb-103">Filtro XPath che specifica il tipo di messaggio da registrare.</span><span class="sxs-lookup"><span data-stu-id="951eb-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="951eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="951eb-104">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="951eb-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="951eb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="951eb-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="951eb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="951eb-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="951eb-107">Attributes</span></span>  
  
|<span data-ttu-id="951eb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="951eb-108">Attribute</span></span>|<span data-ttu-id="951eb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="951eb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="951eb-110">filter</span><span class="sxs-lookup"><span data-stu-id="951eb-110">filter</span></span>|<span data-ttu-id="951eb-111">Stringa che specifica una query su un documento XML definito da un'espressione di XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="951eb-111">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="951eb-112">Per altre informazioni, vedere <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="951eb-112">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="951eb-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="951eb-113">Child Elements</span></span>  
 <span data-ttu-id="951eb-114">No.</span><span class="sxs-lookup"><span data-stu-id="951eb-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="951eb-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="951eb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="951eb-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="951eb-116">Element</span></span>|<span data-ttu-id="951eb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="951eb-117">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="951eb-118">Contiene una raccolta di filtri di XPath usati per controllare il tipo di messaggio registrato.</span><span class="sxs-lookup"><span data-stu-id="951eb-118">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="951eb-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="951eb-119">Remarks</span></span>  
 <span data-ttu-id="951eb-120">I filtri vengono applicati solo al livello di trasporto, specificato da `logMessagesAtTransportLevel` impostato `true`.</span><span class="sxs-lookup"><span data-stu-id="951eb-120">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="951eb-121">I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="951eb-121">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="951eb-122">Per aggiungere un filtro alla raccolta, usare la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="951eb-122">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="951eb-123">Quando sono definiti uno o più filtri, solo i messaggi che corrispondono almeno a uno dei filtri vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="951eb-123">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="951eb-124">Se non è definito alcun filtro, passeranno tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="951eb-124">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="951eb-125">I filtri supportano la sintassi Xpath completa e sono applicati nell'ordine in cui vengono visualizzati nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="951eb-125">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="951eb-126">Un filtro sintatticamente errato determina un'eccezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="951eb-126">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="951eb-127">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="951eb-127">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="951eb-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="951eb-128">Example</span></span>  
 <span data-ttu-id="951eb-129">Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="951eb-129">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="951eb-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="951eb-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="951eb-131">Configurazione della registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="951eb-131">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
