---
title: <add> di <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850373"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="521b4-102">\<add> di \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="521b4-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="521b4-103">Rappresenta un mapping del protocollo predefinito tra uno schema del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="521b4-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="521b4-104">Quando si creano endpoint predefiniti in fase di esecuzione, WCF esamina i mapping configurati e decide il binding da usare per un determinato indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="521b4-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="521b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="521b4-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="521b4-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="521b4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="521b4-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="521b4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="521b4-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="521b4-108">Attributes</span></span>  
  
|<span data-ttu-id="521b4-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="521b4-109">Element</span></span>|<span data-ttu-id="521b4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="521b4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="521b4-111">binding</span><span class="sxs-lookup"><span data-stu-id="521b4-111">binding</span></span>|<span data-ttu-id="521b4-112">Stringa che specifica il tipo di associazione da usare per un endpoint durante la creazione dell'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="521b4-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="521b4-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="521b4-113">bindingConfiguration</span></span>|<span data-ttu-id="521b4-114">Stringa che specifica il nome della sezione di configurazione dell'associazione alla quale fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="521b4-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="521b4-115">scheme</span><span class="sxs-lookup"><span data-stu-id="521b4-115">scheme</span></span>|<span data-ttu-id="521b4-116">Schema del protocollo di trasporto da usare per l'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="521b4-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="521b4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="521b4-117">Child Elements</span></span>  
 <span data-ttu-id="521b4-118">No.</span><span class="sxs-lookup"><span data-stu-id="521b4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="521b4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="521b4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="521b4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="521b4-120">Element</span></span>|<span data-ttu-id="521b4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="521b4-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="521b4-122">Rappresenta una sezione di configurazione per la definizione di mapping dei protocolli predefiniti tra gli schemi del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e le associazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="521b4-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="521b4-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="521b4-123">Example</span></span>  
 <span data-ttu-id="521b4-124">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="521b4-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="521b4-125">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="521b4-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="521b4-126">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="521b4-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="521b4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="521b4-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
