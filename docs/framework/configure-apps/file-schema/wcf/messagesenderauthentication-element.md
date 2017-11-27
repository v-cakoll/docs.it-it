---
title: Elemento &lt;messageSenderAuthentication&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3f73a72398d183e5b758f69edb7bc034f30ed80a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagesenderauthenticationgt-element"></a><span data-ttu-id="1b66b-102">Elemento &lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="1b66b-102">&lt;messageSenderAuthentication&gt; element</span></span>
<span data-ttu-id="1b66b-103">Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1b66b-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="1b66b-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere [rete Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="1b66b-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="1b66b-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1b66b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b66b-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="1b66b-106">\<behaviors></span></span>  
<span data-ttu-id="1b66b-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1b66b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="1b66b-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1b66b-108">\<behavior></span></span>  
<span data-ttu-id="1b66b-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="1b66b-109">\<clientCredentials></span></span>  
<span data-ttu-id="1b66b-110">\<peer ></span><span class="sxs-lookup"><span data-stu-id="1b66b-110">\<peer></span></span>  
<span data-ttu-id="1b66b-111">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1b66b-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b66b-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b66b-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b66b-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b66b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1b66b-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b66b-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b66b-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b66b-115">Attributes</span></span>  
  
|<span data-ttu-id="1b66b-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b66b-116">Attribute</span></span>|<span data-ttu-id="1b66b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b66b-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="1b66b-118">customCertificateValidatorType</span></span>|<span data-ttu-id="1b66b-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1b66b-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1b66b-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="1b66b-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1b66b-121">certifcateValidationMode</span></span>|<span data-ttu-id="1b66b-122">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="1b66b-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="1b66b-123">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="1b66b-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="1b66b-124">revocationMode</span></span>|<span data-ttu-id="1b66b-125">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="1b66b-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="1b66b-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1b66b-126">trustedStoreLocation</span></span>|<span data-ttu-id="1b66b-127">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1b66b-128">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="1b66b-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="1b66b-129">La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="1b66b-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="1b66b-130">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="1b66b-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="1b66b-131">Valore</span><span class="sxs-lookup"><span data-stu-id="1b66b-131">Value</span></span>|<span data-ttu-id="1b66b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b66b-133">String</span><span class="sxs-lookup"><span data-stu-id="1b66b-133">String</span></span>|<span data-ttu-id="1b66b-134">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1b66b-134">Optional.</span></span> <span data-ttu-id="1b66b-135">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="1b66b-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="1b66b-136">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="1b66b-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="1b66b-137">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1b66b-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="1b66b-138">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1b66b-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="1b66b-139">Valore</span><span class="sxs-lookup"><span data-stu-id="1b66b-139">Value</span></span>|<span data-ttu-id="1b66b-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b66b-141">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="1b66b-141">Enumeration</span></span>|<span data-ttu-id="1b66b-142">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1b66b-142">Optional.</span></span> <span data-ttu-id="1b66b-143">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="1b66b-144">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="1b66b-145">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="1b66b-146">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1b66b-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="1b66b-147">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="1b66b-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="1b66b-148">Valore</span><span class="sxs-lookup"><span data-stu-id="1b66b-148">Value</span></span>|<span data-ttu-id="1b66b-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b66b-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="1b66b-150">Enumeration</span></span>|<span data-ttu-id="1b66b-151">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="1b66b-152">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="1b66b-153">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1b66b-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="1b66b-154">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1b66b-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="1b66b-155">Valore</span><span class="sxs-lookup"><span data-stu-id="1b66b-155">Value</span></span>|<span data-ttu-id="1b66b-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b66b-157">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="1b66b-157">Enumeration</span></span>|<span data-ttu-id="1b66b-158">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1b66b-159">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="1b66b-160">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="1b66b-161">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="1b66b-162">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b66b-163">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b66b-163">Child Elements</span></span>  
 <span data-ttu-id="1b66b-164">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1b66b-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b66b-165">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b66b-165">Parent Elements</span></span>  
  
|<span data-ttu-id="1b66b-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b66b-166">Element</span></span>|<span data-ttu-id="1b66b-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b66b-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b66b-168">\<peer ></span><span class="sxs-lookup"><span data-stu-id="1b66b-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="1b66b-169">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="1b66b-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b66b-170">Note</span><span class="sxs-lookup"><span data-stu-id="1b66b-170">Remarks</span></span>  
 <span data-ttu-id="1b66b-171">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="1b66b-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="1b66b-172">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dal [ \<certificato >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="1b66b-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="1b66b-173">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="1b66b-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="1b66b-174">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="1b66b-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b66b-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b66b-175">Example</span></span>  
 <span data-ttu-id="1b66b-176">Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1b66b-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
      <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
        <messageSenderAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
       <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b66b-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b66b-177">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="1b66b-178">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="1b66b-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1b66b-179">Rete peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="1b66b-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="1b66b-180">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="1b66b-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="1b66b-181">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="1b66b-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="1b66b-182">Protezione delle applicazioni del canale Peer</span><span class="sxs-lookup"><span data-stu-id="1b66b-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
