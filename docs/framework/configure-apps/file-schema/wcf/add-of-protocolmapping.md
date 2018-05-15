---
title: '&lt;add&gt; di &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: b9559a6921bdededf760f54f58abadb46612b174
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="3a654-102">&lt;add&gt; di &lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="3a654-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="3a654-103">Rappresenta un mapping del protocollo predefinito tra una combinazione di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3a654-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="3a654-104">Durante la creazione di endpoint predefiniti in fase di esecuzione, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analizza i mapping configurati e determina l'associazione da usare per un particolare indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="3a654-104">When creating default endpoints at runtime, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="3a654-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a654-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3a654-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="3a654-106">\<protocolMapping></span></span>  
<span data-ttu-id="3a654-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3a654-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a654-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a654-108">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a654-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a654-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3a654-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a654-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a654-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a654-111">Attributes</span></span>  
  
|<span data-ttu-id="3a654-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a654-112">Element</span></span>|<span data-ttu-id="3a654-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a654-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a654-114">associazione</span><span class="sxs-lookup"><span data-stu-id="3a654-114">binding</span></span>|<span data-ttu-id="3a654-115">Stringa che specifica il tipo di associazione da usare per un endpoint durante la creazione dell'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a654-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="3a654-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a654-116">bindingConfiguration</span></span>|<span data-ttu-id="3a654-117">Stringa che specifica il nome della sezione di configurazione dell'associazione alla quale fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="3a654-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="3a654-118">scheme</span><span class="sxs-lookup"><span data-stu-id="3a654-118">scheme</span></span>|<span data-ttu-id="3a654-119">Schema del protocollo di trasporto da usare per l'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a654-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a654-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a654-120">Child Elements</span></span>  
 <span data-ttu-id="3a654-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3a654-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a654-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a654-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3a654-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a654-123">Element</span></span>|<span data-ttu-id="3a654-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a654-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a654-125">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="3a654-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="3a654-126">Rappresenta una sezione di configurazione per la definizione dei mapping di protocolli predefiniti tra gli schemi di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e le associazioni di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3a654-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3a654-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a654-127">Example</span></span>  
 <span data-ttu-id="3a654-128">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="3a654-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="3a654-129">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="3a654-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="3a654-130">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="3a654-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a654-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a654-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
