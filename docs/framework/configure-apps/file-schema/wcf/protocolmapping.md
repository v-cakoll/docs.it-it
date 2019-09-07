---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400014"
---
# <a name="protocolmapping"></a><span data-ttu-id="49331-101">\<> protocolMapping</span><span class="sxs-lookup"><span data-stu-id="49331-101">\<protocolMapping></span></span>
<span data-ttu-id="49331-102">Rappresenta una sezione di configurazione per la definizione di un set di mapping dei protocolli predefiniti tra gli schemi del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e le associazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="49331-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="49331-103">Quando si creano endpoint predefiniti in fase di esecuzione, Windows Communication Foundation (WCF) esamina i mapping configurati e decide il binding da usare per un indirizzo specifico.</span><span class="sxs-lookup"><span data-stu-id="49331-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="49331-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="49331-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="49331-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="49331-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="49331-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> protocolMapping**</span><span class="sxs-lookup"><span data-stu-id="49331-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49331-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49331-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49331-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="49331-108">Attributes and Elements</span></span>  
 <span data-ttu-id="49331-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="49331-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49331-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="49331-110">Attributes</span></span>  
 <span data-ttu-id="49331-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="49331-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49331-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="49331-112">Child Elements</span></span>  
  
|<span data-ttu-id="49331-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="49331-113">Element</span></span>|<span data-ttu-id="49331-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="49331-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49331-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="49331-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="49331-116">Contiene un mapping del protocollo predefinito tra uno schema del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e un'associazione WCF.</span><span class="sxs-lookup"><span data-stu-id="49331-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49331-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="49331-117">Parent Elements</span></span>  
  
|<span data-ttu-id="49331-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="49331-118">Element</span></span>|<span data-ttu-id="49331-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49331-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49331-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49331-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="49331-121">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="49331-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49331-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="49331-122">Example</span></span>  
 <span data-ttu-id="49331-123">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="49331-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="49331-124">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="49331-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="49331-125">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="49331-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49331-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49331-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
