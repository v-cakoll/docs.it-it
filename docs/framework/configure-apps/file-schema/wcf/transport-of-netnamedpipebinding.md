---
title: <transport> di <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735967"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="29702-102">\<> di trasporto di \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="29702-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="29702-103">Definisce le impostazioni di sicurezza del trasporto per una named pipe.</span><span class="sxs-lookup"><span data-stu-id="29702-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="29702-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29702-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="29702-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="29702-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="29702-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="29702-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="29702-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetNamedPipeBinding**](netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="29702-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="29702-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="29702-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="29702-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="29702-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="29702-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport** ></span><span class="sxs-lookup"><span data-stu-id="29702-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29702-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29702-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29702-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="29702-112">Attributes and Elements</span></span>  
 <span data-ttu-id="29702-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="29702-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29702-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="29702-114">Attributes</span></span>  
  
|<span data-ttu-id="29702-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="29702-115">Attribute</span></span>|<span data-ttu-id="29702-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29702-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29702-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="29702-117">protectionLevel</span></span>|<span data-ttu-id="29702-118">Definisce il livello di protezione della named pipe.</span><span class="sxs-lookup"><span data-stu-id="29702-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="29702-119">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="29702-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="29702-120">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="29702-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="29702-121">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="29702-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29702-122">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="29702-122">-   None: No protection.</span></span><br /><span data-ttu-id="29702-123">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="29702-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="29702-124">-EncryptAndSign: i messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="29702-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="29702-125">Il valore predefinito è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="29702-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29702-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="29702-126">Child Elements</span></span>  
 <span data-ttu-id="29702-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="29702-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29702-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="29702-128">Parent Elements</span></span>  
  
|<span data-ttu-id="29702-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="29702-129">Element</span></span>|<span data-ttu-id="29702-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29702-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29702-131">\<security ></span><span class="sxs-lookup"><span data-stu-id="29702-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="29702-132">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="29702-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29702-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29702-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="29702-134">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="29702-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="29702-135">Associazioni</span><span class="sxs-lookup"><span data-stu-id="29702-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="29702-136">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="29702-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="29702-137">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="29702-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="29702-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="29702-138">\<binding></span></span>](bindings.md)
