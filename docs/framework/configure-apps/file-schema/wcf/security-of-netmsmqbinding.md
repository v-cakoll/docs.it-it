---
title: <security> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: acb4d04663d841a9b494153caa180855959c145e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670508"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="2c55a-102">\<sicurezza > di \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="2c55a-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="2c55a-103">Definisce le impostazioni di sicurezza per un'associazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2c55a-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="2c55a-104">e specifica se è stata abilitata la sicurezza basata sul trasporto o la sicurezza SOAP. In tal caso, indica la modalità di autenticazione e i livelli di protezione in uso.</span><span class="sxs-lookup"><span data-stu-id="2c55a-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="2c55a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c55a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c55a-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="2c55a-106">\<bindings></span></span>  
<span data-ttu-id="2c55a-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="2c55a-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="2c55a-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="2c55a-108">\<binding></span></span>  
<span data-ttu-id="2c55a-109">\<security></span><span class="sxs-lookup"><span data-stu-id="2c55a-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c55a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c55a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c55a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2c55a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2c55a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2c55a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c55a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2c55a-113">Attributes</span></span>  
  
|<span data-ttu-id="2c55a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2c55a-114">Attribute</span></span>|<span data-ttu-id="2c55a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c55a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c55a-116">modalità</span><span class="sxs-lookup"><span data-stu-id="2c55a-116">mode</span></span>|<span data-ttu-id="2c55a-117">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2c55a-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="2c55a-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="2c55a-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2c55a-119">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c55a-119">-   None: This disables security.</span></span><br /><span data-ttu-id="2c55a-120">-Transport: Protezione e autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="2c55a-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="2c55a-121">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="2c55a-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="2c55a-122">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c55a-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="2c55a-123">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c55a-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="2c55a-124">-Messaggio: Specifica protezione end-end dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c55a-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="2c55a-125">A livello del trasporto non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c55a-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="2c55a-126">È simile alla sicurezza offerta da altre associazioni standard.</span><span class="sxs-lookup"><span data-stu-id="2c55a-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="2c55a-127">-Entrambi: Offre sicurezza a livello di messaggistica SOAP sia il trasporto.</span><span class="sxs-lookup"><span data-stu-id="2c55a-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="2c55a-128">A entrambi i livelli è richiesta la stessa credenziale.</span><span class="sxs-lookup"><span data-stu-id="2c55a-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="2c55a-129">L'impostazione predefinita è Transport.</span><span class="sxs-lookup"><span data-stu-id="2c55a-129">The default value is Transport.</span></span> <span data-ttu-id="2c55a-130">L'attributo è di tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2c55a-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c55a-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2c55a-131">Child Elements</span></span>  
  
|<span data-ttu-id="2c55a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c55a-132">Element</span></span>|<span data-ttu-id="2c55a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c55a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c55a-134">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="2c55a-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="2c55a-135">Definisce le impostazioni di sicurezza per il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="2c55a-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="2c55a-136">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="2c55a-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="2c55a-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="2c55a-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="2c55a-138">Definisce le impostazioni di sicurezza per il trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2c55a-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="2c55a-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2c55a-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c55a-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2c55a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2c55a-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c55a-141">Element</span></span>|<span data-ttu-id="2c55a-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c55a-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c55a-143">binding</span><span class="sxs-lookup"><span data-stu-id="2c55a-143">binding</span></span>|<span data-ttu-id="2c55a-144">L'elemento di associazione del [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c55a-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c55a-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c55a-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="2c55a-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2c55a-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2c55a-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="2c55a-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2c55a-148">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="2c55a-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2c55a-149">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="2c55a-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2c55a-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="2c55a-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="2c55a-151">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="2c55a-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
