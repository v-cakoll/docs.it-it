---
title: <security> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738613"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="0b9f6-102">\<security> di \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="0b9f6-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="0b9f6-103">Definisce le funzionalità di sicurezza di [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0b9f6-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="0b9f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b9f6-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b9f6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0b9f6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0b9f6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b9f6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0b9f6-107">Attributes</span></span>  
  
|<span data-ttu-id="0b9f6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0b9f6-108">Attribute</span></span>|<span data-ttu-id="0b9f6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b9f6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b9f6-110">mode</span><span class="sxs-lookup"><span data-stu-id="0b9f6-110">mode</span></span>|<span data-ttu-id="0b9f6-111">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-111">-   Optional.</span></span> <span data-ttu-id="0b9f6-112">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="0b9f6-113">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-113">The default value is `Message`.</span></span> <span data-ttu-id="0b9f6-114">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0b9f6-115">Attributo Mode</span><span class="sxs-lookup"><span data-stu-id="0b9f6-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="0b9f6-116">Valore</span><span class="sxs-lookup"><span data-stu-id="0b9f6-116">Value</span></span>|<span data-ttu-id="0b9f6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b9f6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b9f6-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="0b9f6-118">None</span></span>|<span data-ttu-id="0b9f6-119">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-119">Security is disabled.</span></span>|  
|<span data-ttu-id="0b9f6-120">Message</span><span class="sxs-lookup"><span data-stu-id="0b9f6-120">Message</span></span>|<span data-ttu-id="0b9f6-121">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b9f6-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0b9f6-122">Child Elements</span></span>  
  
|<span data-ttu-id="0b9f6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b9f6-123">Element</span></span>|<span data-ttu-id="0b9f6-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b9f6-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="0b9f6-125">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="0b9f6-126">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b9f6-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0b9f6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0b9f6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b9f6-128">Element</span></span>|<span data-ttu-id="0b9f6-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b9f6-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0b9f6-130">Definisce tutte le funzionalità di associazione di [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0b9f6-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b9f6-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="0b9f6-131">Remarks</span></span>  
 <span data-ttu-id="0b9f6-132">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="0b9f6-133">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="0b9f6-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9f6-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0b9f6-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="0b9f6-135">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="0b9f6-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0b9f6-136">Binding</span><span class="sxs-lookup"><span data-stu-id="0b9f6-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0b9f6-137">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="0b9f6-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0b9f6-138">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="0b9f6-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
