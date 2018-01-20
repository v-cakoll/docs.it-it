---
title: '&lt;transport&gt; di &lt;netMsmqBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 611d6730695c2e353782d11cb74d391107c02c35
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="41249-102">&lt;transport&gt; di &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="41249-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="41249-103">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="41249-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="41249-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="41249-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="41249-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="41249-105">\<bindings></span></span>  
<span data-ttu-id="41249-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="41249-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="41249-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="41249-107">\<binding></span></span>  
<span data-ttu-id="41249-108">\<security></span><span class="sxs-lookup"><span data-stu-id="41249-108">\<security></span></span>  
<span data-ttu-id="41249-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="41249-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41249-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41249-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41249-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="41249-111">Attributes and Elements</span></span>  
 <span data-ttu-id="41249-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="41249-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41249-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="41249-113">Attributes</span></span>  
  
|<span data-ttu-id="41249-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="41249-114">Attribute</span></span>|<span data-ttu-id="41249-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41249-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41249-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="41249-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="41249-117">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="41249-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="41249-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="41249-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41249-119">-None: Nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41249-119">-   None: No authentication.</span></span><br /><span data-ttu-id="41249-120">-WindowsDomain: Il meccanismo di autenticazione Usa Active Directory per recuperare il certificato x. 509 per l'identificatore di sicurezza associata al messaggio.</span><span class="sxs-lookup"><span data-stu-id="41249-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="41249-121">Questo viene quindi utilizzo per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere sulla coda.</span><span class="sxs-lookup"><span data-stu-id="41249-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="41249-122">-Certificate: Il canale recupera il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="41249-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="41249-123">Il valore predefinito è `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="41249-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="41249-124">Se questo attributo viene impostato su `None`, anche l'attributo dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="41249-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="41249-125">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="41249-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="41249-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="41249-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="41249-127">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="41249-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="41249-128">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="41249-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41249-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="41249-129">-   RC4Stream</span></span><br /><span data-ttu-id="41249-130">-   AES</span><span class="sxs-lookup"><span data-stu-id="41249-130">-   AES</span></span><br /><span data-ttu-id="41249-131">-Il valore predefinito è `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="41249-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="41249-132">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="41249-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="41249-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="41249-133">msmqProtectionLevel</span></span>|<span data-ttu-id="41249-134">Specifica il metodo di sicurezza dei messaggi al livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="41249-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="41249-135">La crittografia assicura l'integrità del messaggio, mentre la firma e la crittografa assicurano l'integrità del messaggio e il non ripudio.</span><span class="sxs-lookup"><span data-stu-id="41249-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="41249-136">Ciò significa che il messaggio proviene effettivamente dal mittente e il mittente è quello indicato.</span><span class="sxs-lookup"><span data-stu-id="41249-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="41249-137">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="41249-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41249-138">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="41249-138">-   None: No protection.</span></span><br /><span data-ttu-id="41249-139">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="41249-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="41249-140">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="41249-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="41249-141">-Il valore predefinito è `Sign`.</span><span class="sxs-lookup"><span data-stu-id="41249-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="41249-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="41249-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="41249-143">Specifica l'algoritmo hash da usare per il calcolo del digest del messaggio.</span><span class="sxs-lookup"><span data-stu-id="41249-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="41249-144">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="41249-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41249-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="41249-145">-   MD5</span></span><br /><span data-ttu-id="41249-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="41249-146">-   SHA1</span></span><br /><span data-ttu-id="41249-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="41249-147">-   SHA256</span></span><br /><span data-ttu-id="41249-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="41249-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="41249-149">Il valore predefinito è `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="41249-149">The default is `SHA1`.</span></span> <span data-ttu-id="41249-150">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="41249-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41249-151">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="41249-151">Child Elements</span></span>  
 <span data-ttu-id="41249-152">nessuno</span><span class="sxs-lookup"><span data-stu-id="41249-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41249-153">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="41249-153">Parent Elements</span></span>  
  
|<span data-ttu-id="41249-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="41249-154">Element</span></span>|<span data-ttu-id="41249-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41249-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41249-156">\<security></span><span class="sxs-lookup"><span data-stu-id="41249-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="41249-157">Definisce le impostazioni di sicurezza del trasporto per i trasporti in coda.</span><span class="sxs-lookup"><span data-stu-id="41249-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41249-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41249-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="41249-159">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="41249-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="41249-160">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="41249-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="41249-161">Associazioni</span><span class="sxs-lookup"><span data-stu-id="41249-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="41249-162">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="41249-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="41249-163">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="41249-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="41249-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="41249-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
