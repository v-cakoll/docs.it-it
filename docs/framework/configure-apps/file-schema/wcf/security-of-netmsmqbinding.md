---
title: <security> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738672"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="be403-102">\<security> di \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="be403-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="be403-103">Definisce le impostazioni di sicurezza per un'associazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="be403-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="be403-104">e specifica se è stata abilitata la sicurezza basata sul trasporto o la sicurezza SOAP. In tal caso, indica la modalità di autenticazione e i livelli di protezione in uso.</span><span class="sxs-lookup"><span data-stu-id="be403-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="be403-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be403-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be403-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="be403-106">Attributes and Elements</span></span>  
 <span data-ttu-id="be403-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="be403-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be403-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="be403-108">Attributes</span></span>  
  
|<span data-ttu-id="be403-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="be403-109">Attribute</span></span>|<span data-ttu-id="be403-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be403-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be403-111">mode</span><span class="sxs-lookup"><span data-stu-id="be403-111">mode</span></span>|<span data-ttu-id="be403-112">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="be403-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="be403-113">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="be403-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="be403-114">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be403-114">-   None: This disables security.</span></span><br /><span data-ttu-id="be403-115">-Transport: la protezione e l'autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="be403-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="be403-116">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="be403-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="be403-117">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be403-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="be403-118">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be403-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="be403-119">-Message: specifica la sicurezza dell'applicazione end-end.</span><span class="sxs-lookup"><span data-stu-id="be403-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="be403-120">A livello del trasporto non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be403-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="be403-121">È simile alla sicurezza offerta da altre associazioni standard.</span><span class="sxs-lookup"><span data-stu-id="be403-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="be403-122">-Both: offre sicurezza a livello di trasporto e messaggistica SOAP.</span><span class="sxs-lookup"><span data-stu-id="be403-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="be403-123">A entrambi i livelli è richiesta la stessa credenziale.</span><span class="sxs-lookup"><span data-stu-id="be403-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="be403-124">L'impostazione predefinita è Transport.</span><span class="sxs-lookup"><span data-stu-id="be403-124">The default value is Transport.</span></span> <span data-ttu-id="be403-125">L'attributo è di tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="be403-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be403-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="be403-126">Child Elements</span></span>  
  
|<span data-ttu-id="be403-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="be403-127">Element</span></span>|<span data-ttu-id="be403-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be403-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="be403-129">Definisce le impostazioni di sicurezza per il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="be403-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="be403-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="be403-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="be403-131">Definisce le impostazioni di sicurezza per il trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="be403-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="be403-132">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="be403-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be403-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="be403-133">Parent Elements</span></span>  
  
|<span data-ttu-id="be403-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="be403-134">Element</span></span>|<span data-ttu-id="be403-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be403-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be403-136">binding</span><span class="sxs-lookup"><span data-stu-id="be403-136">binding</span></span>|<span data-ttu-id="be403-137">Elemento di associazione di[\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="be403-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be403-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="be403-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="be403-139">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="be403-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="be403-140">Binding</span><span class="sxs-lookup"><span data-stu-id="be403-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="be403-141">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="be403-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="be403-142">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="be403-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="be403-143">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="be403-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
