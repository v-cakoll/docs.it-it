---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400014"
---
# \<protocolMapping>
<span data-ttu-id="b390f-101">Rappresenta una sezione di configurazione per la definizione di un set di mapping dei protocolli predefiniti tra gli schemi dei protocolli di trasporto (ad esempio http, net.tcp, net.pipe e così via) e le associazioni di WCF.</span><span class="sxs-lookup"><span data-stu-id="b390f-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="b390f-102">Quando si creano endpoint predefiniti in fase di esecuzione, Windows Communication Foundation (WCF) esamina i mapping configurati e decide il binding da usare per un indirizzo specifico.</span><span class="sxs-lookup"><span data-stu-id="b390f-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="b390f-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b390f-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b390f-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b390f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="b390f-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b390f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b390f-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="b390f-106">Attributes</span></span>  
 <span data-ttu-id="b390f-107">No.</span><span class="sxs-lookup"><span data-stu-id="b390f-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b390f-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b390f-108">Child Elements</span></span>  
  
|<span data-ttu-id="b390f-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="b390f-109">Element</span></span>|<span data-ttu-id="b390f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b390f-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="b390f-111">Contiene un mapping del protocollo predefinito tra lo schema di un protocollo di trasporto (ad esempio http, net.tcp, net.pipe e così via) e l'associazione di WCF. </span><span class="sxs-lookup"><span data-stu-id="b390f-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b390f-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b390f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b390f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b390f-113">Element</span></span>|<span data-ttu-id="b390f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b390f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="b390f-115">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="b390f-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b390f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b390f-116">Example</span></span>  
 <span data-ttu-id="b390f-117">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="b390f-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="b390f-118">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="b390f-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="b390f-119">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="b390f-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b390f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b390f-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
