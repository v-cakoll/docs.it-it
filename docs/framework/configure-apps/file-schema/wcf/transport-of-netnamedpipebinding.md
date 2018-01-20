---
title: '&lt;transport&gt; di &lt;netNamedPipeBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84811c70f2f3608c10d8886900169f804a8c9b62
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="1011f-102">&lt;transport&gt; di &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1011f-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="1011f-103">Definisce le impostazioni di sicurezza del trasporto per una named pipe.</span><span class="sxs-lookup"><span data-stu-id="1011f-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="1011f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1011f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1011f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1011f-105">\<bindings></span></span>  
<span data-ttu-id="1011f-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="1011f-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="1011f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1011f-107">\<binding></span></span>  
<span data-ttu-id="1011f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1011f-108">\<security></span></span>  
<span data-ttu-id="1011f-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="1011f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1011f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1011f-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1011f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1011f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1011f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1011f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1011f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1011f-113">Attributes</span></span>  
  
|<span data-ttu-id="1011f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1011f-114">Attribute</span></span>|<span data-ttu-id="1011f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1011f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1011f-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="1011f-116">protectionLevel</span></span>|<span data-ttu-id="1011f-117">Definisce il livello di protezione della named pipe.</span><span class="sxs-lookup"><span data-stu-id="1011f-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="1011f-118">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="1011f-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1011f-119">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="1011f-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="1011f-120">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1011f-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1011f-121">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="1011f-121">-   None: No protection.</span></span><br /><span data-ttu-id="1011f-122">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="1011f-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1011f-123">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="1011f-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1011f-124">Il valore predefinito è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="1011f-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1011f-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1011f-125">Child Elements</span></span>  
 <span data-ttu-id="1011f-126">nessuno</span><span class="sxs-lookup"><span data-stu-id="1011f-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1011f-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1011f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1011f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1011f-128">Element</span></span>|<span data-ttu-id="1011f-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1011f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1011f-130">\<security></span><span class="sxs-lookup"><span data-stu-id="1011f-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="1011f-131">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="1011f-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1011f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1011f-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="1011f-133">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1011f-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1011f-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1011f-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1011f-135">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1011f-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1011f-136">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1011f-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1011f-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="1011f-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
