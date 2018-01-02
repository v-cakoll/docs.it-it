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
ms.workload: dotnet
ms.openlocfilehash: 03cd07681c111f51a4ea02ac46354fa9a19f42d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="03d51-102">&lt;transport&gt; di &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="03d51-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="03d51-103">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="03d51-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="03d51-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="03d51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03d51-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="03d51-105">\<bindings></span></span>  
<span data-ttu-id="03d51-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="03d51-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="03d51-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="03d51-107">\<binding></span></span>  
<span data-ttu-id="03d51-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="03d51-108">\<security></span></span>  
<span data-ttu-id="03d51-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="03d51-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d51-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03d51-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03d51-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03d51-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03d51-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03d51-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03d51-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="03d51-113">Attributes</span></span>  
  
|<span data-ttu-id="03d51-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="03d51-114">Attribute</span></span>|<span data-ttu-id="03d51-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03d51-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="03d51-116">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="03d51-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="03d51-117">Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="03d51-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="03d51-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="03d51-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="03d51-119">-None: Nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="03d51-119">-   None: No authentication.</span></span><br /><span data-ttu-id="03d51-120">-WindowsDomain: Il meccanismo di autenticazione Usa Active Directory per ottenere il certificato x. 509 per il SID associato al messaggio.</span><span class="sxs-lookup"><span data-stu-id="03d51-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="03d51-121">Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.</span><span class="sxs-lookup"><span data-stu-id="03d51-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="03d51-122">-Certificate: Il canale Ottiene il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="03d51-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="03d51-123">Il valore predefinito è WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="03d51-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="03d51-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="03d51-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="03d51-125">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="03d51-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="03d51-126">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="03d51-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="03d51-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="03d51-127">-   RC4Stream</span></span><br /><span data-ttu-id="03d51-128">-AES</span><span class="sxs-lookup"><span data-stu-id="03d51-128">-   AES</span></span><br /><br /> <span data-ttu-id="03d51-129">Il valore predefinito è RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="03d51-129">The default value is RC4Stream.</span></span> <span data-ttu-id="03d51-130">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="03d51-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="03d51-131">Specifica come viene protetto il messaggio a livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="03d51-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="03d51-132">La crittografia assicura l'integrità del messaggio mentre EncryptAndSign assicura sia l'integrità che il non ripudio del messaggio; ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dichiara di essere.</span><span class="sxs-lookup"><span data-stu-id="03d51-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="03d51-133">-I valori validi includono:</span><span class="sxs-lookup"><span data-stu-id="03d51-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="03d51-134">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="03d51-134">-   None: No protection.</span></span><br /><span data-ttu-id="03d51-135">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="03d51-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="03d51-136">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="03d51-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="03d51-137">Il valore predefinito è Sign.</span><span class="sxs-lookup"><span data-stu-id="03d51-137">The default value is Sign.</span></span> <span data-ttu-id="03d51-138">L'attributo è di tipo ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="03d51-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="03d51-139">-Specifica l'algoritmo da utilizzare nel calcolo del digest come parte delle firme.</span><span class="sxs-lookup"><span data-stu-id="03d51-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="03d51-140">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="03d51-140">Valid values include the following:</span></span><br /><span data-ttu-id="03d51-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="03d51-141">-   MD5</span></span><br /><span data-ttu-id="03d51-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="03d51-142">-   SHA1</span></span><br /><span data-ttu-id="03d51-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="03d51-143">-   SHA256</span></span><br /><span data-ttu-id="03d51-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="03d51-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="03d51-145">Il valore predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="03d51-145">The default value is SHA1.</span></span> <span data-ttu-id="03d51-146">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="03d51-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03d51-147">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03d51-147">Child Elements</span></span>  
 <span data-ttu-id="03d51-148">None</span><span class="sxs-lookup"><span data-stu-id="03d51-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03d51-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03d51-149">Parent Elements</span></span>  
  
|<span data-ttu-id="03d51-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="03d51-150">Element</span></span>|<span data-ttu-id="03d51-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03d51-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03d51-152">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="03d51-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="03d51-153">Definisce le impostazioni di sicurezza per un'associazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="03d51-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03d51-154">Note</span><span class="sxs-lookup"><span data-stu-id="03d51-154">Remarks</span></span>  
 <span data-ttu-id="03d51-155">Questo elemento incapsula le impostazioni di sicurezza per il trasporto di integrazione del servizio di accodamento di messaggi.</span><span class="sxs-lookup"><span data-stu-id="03d51-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="03d51-156">Le impostazioni sono le stesse per l'integrazione di accodamento messaggi e trasporti in coda.</span><span class="sxs-lookup"><span data-stu-id="03d51-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="03d51-157">Consente di impostare la modalità di autenticazione, l'algoritmo di crittografia, l'algoritmo hash protetto e il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="03d51-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d51-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03d51-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="03d51-159">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="03d51-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="03d51-160">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="03d51-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="03d51-161">Associazioni</span><span class="sxs-lookup"><span data-stu-id="03d51-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="03d51-162">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="03d51-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="03d51-163">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="03d51-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="03d51-164">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="03d51-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
