---
title: <add> di <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850373"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="f9168-102">\<aggiungere > di \<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="f9168-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="f9168-103">Rappresenta un mapping del protocollo predefinito tra uno schema del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f9168-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="f9168-104">Quando si creano endpoint predefiniti in fase di esecuzione, WCF esamina i mapping configurati e decide il binding da usare per un determinato indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f9168-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="f9168-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9168-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9168-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f9168-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f9168-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> protocolMapping**](protocolmapping.md)</span><span class="sxs-lookup"><span data-stu-id="f9168-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)</span></span>\
<span data-ttu-id="f9168-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="f9168-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9168-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9168-109">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9168-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9168-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f9168-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9168-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9168-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9168-112">Attributes</span></span>  
  
|<span data-ttu-id="f9168-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9168-113">Element</span></span>|<span data-ttu-id="f9168-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9168-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f9168-115">binding</span><span class="sxs-lookup"><span data-stu-id="f9168-115">binding</span></span>|<span data-ttu-id="f9168-116">Stringa che specifica il tipo di associazione da usare per un endpoint durante la creazione dell'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="f9168-116">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="f9168-117">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9168-117">bindingConfiguration</span></span>|<span data-ttu-id="f9168-118">Stringa che specifica il nome della sezione di configurazione dell'associazione alla quale fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="f9168-118">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="f9168-119">scheme</span><span class="sxs-lookup"><span data-stu-id="f9168-119">scheme</span></span>|<span data-ttu-id="f9168-120">Schema del protocollo di trasporto da usare per l'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="f9168-120">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9168-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9168-121">Child Elements</span></span>  
 <span data-ttu-id="f9168-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f9168-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9168-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9168-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f9168-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9168-124">Element</span></span>|<span data-ttu-id="f9168-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f9168-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9168-126">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="f9168-126">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="f9168-127">Rappresenta una sezione di configurazione per la definizione di mapping dei protocolli predefiniti tra gli schemi del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e le associazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f9168-127">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f9168-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9168-128">Example</span></span>  
 <span data-ttu-id="f9168-129">Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9168-129">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="f9168-130">È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9168-130">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="f9168-131">In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.</span><span class="sxs-lookup"><span data-stu-id="f9168-131">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9168-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9168-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
