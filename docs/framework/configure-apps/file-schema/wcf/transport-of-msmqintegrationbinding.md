---
title: '&lt;transport&gt; di &lt;msmqIntegrationBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27b2ade7c9033ca82d3249ef18f1004e30c30025
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="436f4-102">&lt;transport&gt; di &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="436f4-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="436f4-103">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="436f4-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="436f4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="436f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="436f4-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="436f4-105">\<bindings></span></span>  
<span data-ttu-id="436f4-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="436f4-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="436f4-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="436f4-107">\<binding></span></span>  
<span data-ttu-id="436f4-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="436f4-108">\<security></span></span>  
<span data-ttu-id="436f4-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="436f4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="436f4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="436f4-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="436f4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="436f4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="436f4-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="436f4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="436f4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="436f4-113">Attributes</span></span>  
  
|<span data-ttu-id="436f4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="436f4-114">Attribute</span></span>|<span data-ttu-id="436f4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="436f4-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="436f4-116">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="436f4-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="436f4-117">Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="436f4-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="436f4-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="436f4-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="436f4-119">-None: Nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="436f4-119">-   None: No authentication.</span></span><br /><span data-ttu-id="436f4-120">-WindowsDomain: Il meccanismo di autenticazione Usa Active Directory per ottenere il certificato x. 509 per il SID associato al messaggio.</span><span class="sxs-lookup"><span data-stu-id="436f4-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="436f4-121">Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.</span><span class="sxs-lookup"><span data-stu-id="436f4-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="436f4-122">-Certificate: Il canale Ottiene il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="436f4-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="436f4-123">Il valore predefinito è WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="436f4-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="436f4-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="436f4-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="436f4-125">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="436f4-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="436f4-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="436f4-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="436f4-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="436f4-127">-   RC4Stream</span></span><br /><span data-ttu-id="436f4-128">-AES</span><span class="sxs-lookup"><span data-stu-id="436f4-128">-   AES</span></span><br /><br /> <span data-ttu-id="436f4-129">Il valore predefinito è RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="436f4-129">The default value is RC4Stream.</span></span> <span data-ttu-id="436f4-130">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="436f4-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="436f4-131">Specifica come viene protetto il messaggio a livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="436f4-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="436f4-132">La crittografia assicura l'integrità del messaggio mentre EncryptAndSign assicura sia l'integrità che il non ripudio del messaggio; ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dichiara di essere.</span><span class="sxs-lookup"><span data-stu-id="436f4-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="436f4-133">-I valori validi includono:</span><span class="sxs-lookup"><span data-stu-id="436f4-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="436f4-134">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="436f4-134">-   None: No protection.</span></span><br /><span data-ttu-id="436f4-135">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="436f4-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="436f4-136">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="436f4-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="436f4-137">Il valore predefinito è Sign.</span><span class="sxs-lookup"><span data-stu-id="436f4-137">The default value is Sign.</span></span> <span data-ttu-id="436f4-138">L'attributo è di tipo ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="436f4-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="436f4-139">-Specifica l'algoritmo da utilizzare nel calcolo del digest come parte delle firme.</span><span class="sxs-lookup"><span data-stu-id="436f4-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="436f4-140">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="436f4-140">Valid values include the following:</span></span><br /><span data-ttu-id="436f4-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="436f4-141">-   MD5</span></span><br /><span data-ttu-id="436f4-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="436f4-142">-   SHA1</span></span><br /><span data-ttu-id="436f4-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="436f4-143">-   SHA256</span></span><br /><span data-ttu-id="436f4-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="436f4-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="436f4-145">Il valore predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="436f4-145">The default value is SHA1.</span></span> <span data-ttu-id="436f4-146">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="436f4-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="436f4-147">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="436f4-147">Child Elements</span></span>  
 <span data-ttu-id="436f4-148">None</span><span class="sxs-lookup"><span data-stu-id="436f4-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="436f4-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="436f4-149">Parent Elements</span></span>  
  
|<span data-ttu-id="436f4-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="436f4-150">Element</span></span>|<span data-ttu-id="436f4-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="436f4-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="436f4-152">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="436f4-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="436f4-153">Definisce le impostazioni di sicurezza per un'associazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="436f4-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="436f4-154">Note</span><span class="sxs-lookup"><span data-stu-id="436f4-154">Remarks</span></span>  
 <span data-ttu-id="436f4-155">Questo elemento incapsula le impostazioni di sicurezza per il trasporto di integrazione del servizio di accodamento di messaggi.</span><span class="sxs-lookup"><span data-stu-id="436f4-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="436f4-156">Le impostazioni sono le stesse per l'integrazione di accodamento messaggi e trasporti in coda.</span><span class="sxs-lookup"><span data-stu-id="436f4-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="436f4-157">Consente di impostare la modalità di autenticazione, l'algoritmo di crittografia, l'algoritmo hash protetto e il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="436f4-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436f4-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="436f4-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="436f4-159">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="436f4-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="436f4-160">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="436f4-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="436f4-161">Associazioni</span><span class="sxs-lookup"><span data-stu-id="436f4-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="436f4-162">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="436f4-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="436f4-163">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="436f4-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="436f4-164">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="436f4-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
