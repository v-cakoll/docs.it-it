---
title: <security> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936550"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="a2d83-102">\<> di sicurezza \<di WSDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2d83-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="a2d83-103">Definisce le funzionalità di sicurezza del [ \<> WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a2d83-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="a2d83-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a2d83-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2d83-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="a2d83-105">\<bindings></span></span>  
<span data-ttu-id="a2d83-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a2d83-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="a2d83-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2d83-107">\<binding></span></span>  
<span data-ttu-id="a2d83-108">\<security></span><span class="sxs-lookup"><span data-stu-id="a2d83-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d83-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2d83-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2d83-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a2d83-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a2d83-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a2d83-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2d83-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a2d83-112">Attributes</span></span>  
  
|<span data-ttu-id="a2d83-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a2d83-113">Attribute</span></span>|<span data-ttu-id="a2d83-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a2d83-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2d83-115">modalità</span><span class="sxs-lookup"><span data-stu-id="a2d83-115">mode</span></span>|<span data-ttu-id="a2d83-116">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="a2d83-116">-   Optional.</span></span> <span data-ttu-id="a2d83-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="a2d83-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a2d83-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="a2d83-118">The default value is `Message`.</span></span> <span data-ttu-id="a2d83-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a2d83-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a2d83-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="a2d83-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="a2d83-121">Valore</span><span class="sxs-lookup"><span data-stu-id="a2d83-121">Value</span></span>|<span data-ttu-id="a2d83-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d83-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2d83-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="a2d83-123">None</span></span>|<span data-ttu-id="a2d83-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="a2d83-124">Security is disabled.</span></span>|  
|<span data-ttu-id="a2d83-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a2d83-125">Message</span></span>|<span data-ttu-id="a2d83-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="a2d83-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2d83-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a2d83-127">Child Elements</span></span>  
  
|<span data-ttu-id="a2d83-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2d83-128">Element</span></span>|<span data-ttu-id="a2d83-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a2d83-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2d83-130">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="a2d83-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="a2d83-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="a2d83-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="a2d83-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="a2d83-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2d83-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a2d83-133">Parent Elements</span></span>  
  
|<span data-ttu-id="a2d83-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2d83-134">Element</span></span>|<span data-ttu-id="a2d83-135">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a2d83-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2d83-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2d83-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a2d83-137">Definisce tutte le funzionalità di associazione del [ \<> WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a2d83-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2d83-138">Note</span><span class="sxs-lookup"><span data-stu-id="a2d83-138">Remarks</span></span>  
 <span data-ttu-id="a2d83-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d83-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a2d83-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="a2d83-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d83-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2d83-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="a2d83-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="a2d83-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a2d83-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a2d83-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a2d83-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a2d83-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a2d83-145">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="a2d83-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a2d83-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2d83-146">\<binding></span></span>](../../../misc/binding.md)
