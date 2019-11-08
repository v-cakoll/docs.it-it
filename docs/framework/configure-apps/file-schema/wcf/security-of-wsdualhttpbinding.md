---
title: <security> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738613"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="56cb6-102">\<> di sicurezza di \<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="56cb6-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="56cb6-103">Definisce le funzionalità di sicurezza della [> WSDualHttpBinding di\<](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="56cb6-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="56cb6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56cb6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56cb6-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="56cb6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="56cb6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="56cb6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="56cb6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**WSDualHttpBinding**](wsdualhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="56cb6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\</span></span>
<span data-ttu-id="56cb6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="56cb6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="56cb6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="56cb6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cb6-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56cb6-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56cb6-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="56cb6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="56cb6-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="56cb6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56cb6-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="56cb6-113">Attributes</span></span>  
  
|<span data-ttu-id="56cb6-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="56cb6-114">Attribute</span></span>|<span data-ttu-id="56cb6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cb6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56cb6-116">modalità</span><span class="sxs-lookup"><span data-stu-id="56cb6-116">mode</span></span>|<span data-ttu-id="56cb6-117">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="56cb6-117">-   Optional.</span></span> <span data-ttu-id="56cb6-118">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="56cb6-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="56cb6-119">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="56cb6-119">The default value is `Message`.</span></span> <span data-ttu-id="56cb6-120">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="56cb6-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="56cb6-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="56cb6-122">Value</span><span class="sxs-lookup"><span data-stu-id="56cb6-122">Value</span></span>|<span data-ttu-id="56cb6-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cb6-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="56cb6-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="56cb6-124">None</span></span>|<span data-ttu-id="56cb6-125">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="56cb6-125">Security is disabled.</span></span>|  
|<span data-ttu-id="56cb6-126">Messaggio</span><span class="sxs-lookup"><span data-stu-id="56cb6-126">Message</span></span>|<span data-ttu-id="56cb6-127">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="56cb6-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56cb6-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="56cb6-128">Child Elements</span></span>  
  
|<span data-ttu-id="56cb6-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="56cb6-129">Element</span></span>|<span data-ttu-id="56cb6-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cb6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56cb6-131">\<message ></span><span class="sxs-lookup"><span data-stu-id="56cb6-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="56cb6-132">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="56cb6-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="56cb6-133">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56cb6-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="56cb6-134">Parent Elements</span></span>  
  
|<span data-ttu-id="56cb6-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="56cb6-135">Element</span></span>|<span data-ttu-id="56cb6-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cb6-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56cb6-137">\<binding ></span><span class="sxs-lookup"><span data-stu-id="56cb6-137">\<binding></span></span>](bindings.md)|<span data-ttu-id="56cb6-138">Definisce tutte le funzionalità di associazione della [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="56cb6-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56cb6-139">Note</span><span class="sxs-lookup"><span data-stu-id="56cb6-139">Remarks</span></span>  
 <span data-ttu-id="56cb6-140">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="56cb6-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="56cb6-141">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="56cb6-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cb6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56cb6-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="56cb6-143">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="56cb6-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="56cb6-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="56cb6-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="56cb6-145">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="56cb6-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="56cb6-146">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="56cb6-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="56cb6-147">\<binding ></span><span class="sxs-lookup"><span data-stu-id="56cb6-147">\<binding></span></span>](bindings.md)
