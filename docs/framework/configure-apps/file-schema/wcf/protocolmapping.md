---
title: '&lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: a376f1eaa7c8790cf2174335749ed3001b403967
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147304"
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="2f52e-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="2f52e-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="2f52e-103">Rappresenta una sezione di configurazione per la definizione di un set di mapping del protocollo predefinito tra gli schemi di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e le associazioni di WCF.</span><span class="sxs-lookup"><span data-stu-id="2f52e-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="2f52e-104">Quando si creano endpoint predefiniti in fase di esecuzione, Windows Communication Foundation (WCF) esamina i mapping configurati e decide l'associazione da utilizzare per un determinato indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="2f52e-104">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="2f52e-105">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="2f52e-105">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="2f52e-106">&nbsp;&nbsp;**\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="2f52e-106">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f52e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f52e-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f52e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f52e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f52e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f52e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f52e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f52e-110">Attributes</span></span>  
 <span data-ttu-id="2f52e-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2f52e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f52e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f52e-112">Child Elements</span></span>  
  
|<span data-ttu-id="2f52e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f52e-113">Element</span></span>|<span data-ttu-id="2f52e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f52e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f52e-115">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="2f52e-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="2f52e-116">Contiene un mapping del protocollo predefinito tra una combinazione di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e un binding WCF.</span><span class="sxs-lookup"><span data-stu-id="2f52e-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f52e-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f52e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2f52e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f52e-118">Element</span></span>|<span data-ttu-id="2f52e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f52e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f52e-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2f52e-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="2f52e-121">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="2f52e-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f52e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f52e-122">Example</span></span>  
 <span data-ttu-id="2f52e-123">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="2f52e-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="2f52e-124">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="2f52e-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="2f52e-125">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="2f52e-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f52e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f52e-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
