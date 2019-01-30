---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 6ec17457c8742fdf17208c6588e0ab70ece7c42a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268672"
---
# <a name="protocolmapping"></a><span data-ttu-id="eb032-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="eb032-101">\<protocolMapping></span></span>
<span data-ttu-id="eb032-102">Rappresenta una sezione di configurazione per la definizione di un set di mapping del protocollo predefinito tra gli schemi di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e le associazioni di WCF.</span><span class="sxs-lookup"><span data-stu-id="eb032-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="eb032-103">Quando si creano endpoint predefiniti in fase di esecuzione, Windows Communication Foundation (WCF) esamina i mapping configurati e decide l'associazione da utilizzare per un determinato indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="eb032-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="eb032-104">**\<system.serviceModel>**</span><span class="sxs-lookup"><span data-stu-id="eb032-104">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="eb032-105">&nbsp;&nbsp;**\<protocolMapping>**</span><span class="sxs-lookup"><span data-stu-id="eb032-105">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb032-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb032-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb032-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eb032-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eb032-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eb032-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb032-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb032-109">Attributes</span></span>  
 <span data-ttu-id="eb032-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb032-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb032-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eb032-111">Child Elements</span></span>  
  
|<span data-ttu-id="eb032-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb032-112">Element</span></span>|<span data-ttu-id="eb032-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb032-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb032-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="eb032-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="eb032-115">Contiene un mapping del protocollo predefinito tra una combinazione di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e un binding WCF.</span><span class="sxs-lookup"><span data-stu-id="eb032-115">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb032-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eb032-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb032-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb032-117">Element</span></span>|<span data-ttu-id="eb032-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb032-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb032-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eb032-119">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="eb032-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="eb032-120">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb032-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb032-121">Example</span></span>  
 <span data-ttu-id="eb032-122">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="eb032-122">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="eb032-123">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="eb032-123">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="eb032-124">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="eb032-124">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb032-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb032-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
