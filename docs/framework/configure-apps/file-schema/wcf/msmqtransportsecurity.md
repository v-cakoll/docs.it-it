---
title: '&lt;msmqTransportSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: eee2cb916d79bf3b79e882cd757b10344121f6b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmsmqtransportsecuritygt"></a><span data-ttu-id="8db10-102">&lt;msmqTransportSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="8db10-102">&lt;msmqTransportSecurity&gt;</span></span>
<span data-ttu-id="8db10-103">Specifica le impostazioni di sicurezza del trasporto MSMQ di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8db10-103">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="8db10-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8db10-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8db10-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="8db10-105">\<bindings></span></span>  
<span data-ttu-id="8db10-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8db10-106">\<customBinding></span></span>  
<span data-ttu-id="8db10-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8db10-107">\<binding></span></span>  
<span data-ttu-id="8db10-108">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="8db10-108">\<msmqIntegration></span></span>  
<span data-ttu-id="8db10-109">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="8db10-109">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db10-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8db10-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8db10-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8db10-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8db10-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8db10-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8db10-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8db10-113">Attributes</span></span>  
  
|<span data-ttu-id="8db10-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8db10-114">Attribute</span></span>|<span data-ttu-id="8db10-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db10-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="8db10-116">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8db10-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="8db10-117">Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="8db10-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="8db10-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8db10-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8db10-119">-None: Nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8db10-119">-   None: No authentication.</span></span><br /><span data-ttu-id="8db10-120">-Windows: Il meccanismo di autenticazione Usa Active Directory per ottenere il certificato x. 509 per il SID associato al messaggio.</span><span class="sxs-lookup"><span data-stu-id="8db10-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="8db10-121">Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.</span><span class="sxs-lookup"><span data-stu-id="8db10-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="8db10-122">-Certificate: Il canale Ottiene il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="8db10-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="8db10-123">L'impostazione predefinita è Windows.</span><span class="sxs-lookup"><span data-stu-id="8db10-123">The default value is Windows.</span></span> <span data-ttu-id="8db10-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="8db10-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="8db10-125">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8db10-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="8db10-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8db10-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8db10-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="8db10-127">-   RC4Stream</span></span><br /><span data-ttu-id="8db10-128">-AES</span><span class="sxs-lookup"><span data-stu-id="8db10-128">-   AES</span></span><br /><br /> <span data-ttu-id="8db10-129">Il valore predefinito è RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="8db10-129">The default value is RC4Stream.</span></span> <span data-ttu-id="8db10-130">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="8db10-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="8db10-131">Specifica come viene protetto il messaggio a livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8db10-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="8db10-132">La crittografia assicura l'integrità del messaggio mentre EncryptAndSign assicura sia l'integrità che il non ripudio del messaggio; ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dichiara di essere.</span><span class="sxs-lookup"><span data-stu-id="8db10-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="8db10-133">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8db10-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8db10-134">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="8db10-134">-   None: No protection.</span></span><br /><span data-ttu-id="8db10-135">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="8db10-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="8db10-136">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="8db10-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="8db10-137">Il valore predefinito è Sign.</span><span class="sxs-lookup"><span data-stu-id="8db10-137">The default value is Sign.</span></span> <span data-ttu-id="8db10-138">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="8db10-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="8db10-139">Specifica l'algoritmo da usare nel calcolo del digest come parte delle firme.</span><span class="sxs-lookup"><span data-stu-id="8db10-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="8db10-140">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="8db10-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8db10-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="8db10-141">-   MD5</span></span><br /><span data-ttu-id="8db10-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="8db10-142">-   SHA1</span></span><br /><span data-ttu-id="8db10-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="8db10-143">-   SHA256</span></span><br /><span data-ttu-id="8db10-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="8db10-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="8db10-145">Il valore predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="8db10-145">The default value is SHA1.</span></span> <span data-ttu-id="8db10-146">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="8db10-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8db10-147">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8db10-147">Child Elements</span></span>  
 <span data-ttu-id="8db10-148">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8db10-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8db10-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8db10-149">Parent Elements</span></span>  
  
|<span data-ttu-id="8db10-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="8db10-150">Element</span></span>|<span data-ttu-id="8db10-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db10-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8db10-152">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="8db10-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="8db10-153">Specifica le impostazioni necessarie per l'interazione con un mittente o un destinatario del sistema di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8db10-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="8db10-154">\<msmqTransport ></span><span class="sxs-lookup"><span data-stu-id="8db10-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="8db10-155">Specifica le proprietà di comunicazione dell'accodamento per un servizio Windows Communication Foundation (WCF) che usa il protocollo MSMQ nativo.</span><span class="sxs-lookup"><span data-stu-id="8db10-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8db10-156">Note</span><span class="sxs-lookup"><span data-stu-id="8db10-156">Remarks</span></span>  
 <span data-ttu-id="8db10-157">Per ulteriori informazioni sulla protezione del trasporto, vedere [la sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="8db10-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db10-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8db10-158">See Also</span></span>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8db10-159">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="8db10-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="8db10-160">Trasporti</span><span class="sxs-lookup"><span data-stu-id="8db10-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="8db10-161">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="8db10-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="8db10-162">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8db10-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8db10-163">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="8db10-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8db10-164">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8db10-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8db10-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8db10-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="8db10-166">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="8db10-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
