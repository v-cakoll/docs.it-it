---
title: Elemento &lt;messageSenderAuthentication&gt;
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 898569796c65a7999583f4faba9f11a6172a5af8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagesenderauthenticationgt-element"></a><span data-ttu-id="bc13f-102">Elemento &lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="bc13f-102">&lt;messageSenderAuthentication&gt; element</span></span>
<span data-ttu-id="bc13f-103">Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="bc13f-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="bc13f-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere [rete Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="bc13f-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="bc13f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bc13f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="bc13f-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="bc13f-106">\<behaviors></span></span>  
<span data-ttu-id="bc13f-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bc13f-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="bc13f-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="bc13f-108">\<behavior></span></span>  
<span data-ttu-id="bc13f-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="bc13f-109">\<clientCredentials></span></span>  
<span data-ttu-id="bc13f-110">\<peer ></span><span class="sxs-lookup"><span data-stu-id="bc13f-110">\<peer></span></span>  
<span data-ttu-id="bc13f-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="bc13f-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc13f-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc13f-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc13f-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bc13f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bc13f-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bc13f-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc13f-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="bc13f-115">Attributes</span></span>  
  
|<span data-ttu-id="bc13f-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="bc13f-116">Attribute</span></span>|<span data-ttu-id="bc13f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc13f-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="bc13f-118">customCertificateValidatorType</span></span>|<span data-ttu-id="bc13f-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bc13f-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="bc13f-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="bc13f-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="bc13f-121">certifcateValidationMode</span></span>|<span data-ttu-id="bc13f-122">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="bc13f-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="bc13f-123">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="bc13f-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="bc13f-124">revocationMode</span></span>|<span data-ttu-id="bc13f-125">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="bc13f-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="bc13f-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="bc13f-126">trustedStoreLocation</span></span>|<span data-ttu-id="bc13f-127">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="bc13f-128">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="bc13f-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="bc13f-129">La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="bc13f-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="bc13f-130">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="bc13f-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="bc13f-131">Valore</span><span class="sxs-lookup"><span data-stu-id="bc13f-131">Value</span></span>|<span data-ttu-id="bc13f-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc13f-133">String</span><span class="sxs-lookup"><span data-stu-id="bc13f-133">String</span></span>|<span data-ttu-id="bc13f-134">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bc13f-134">Optional.</span></span> <span data-ttu-id="bc13f-135">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="bc13f-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="bc13f-136">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="bc13f-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="bc13f-137">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="bc13f-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="bc13f-138">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="bc13f-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="bc13f-139">Valore</span><span class="sxs-lookup"><span data-stu-id="bc13f-139">Value</span></span>|<span data-ttu-id="bc13f-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc13f-141">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bc13f-141">Enumeration</span></span>|<span data-ttu-id="bc13f-142">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bc13f-142">Optional.</span></span> <span data-ttu-id="bc13f-143">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="bc13f-144">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="bc13f-145">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="bc13f-146">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bc13f-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="bc13f-147">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="bc13f-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="bc13f-148">Valore</span><span class="sxs-lookup"><span data-stu-id="bc13f-148">Value</span></span>|<span data-ttu-id="bc13f-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc13f-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bc13f-150">Enumeration</span></span>|<span data-ttu-id="bc13f-151">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="bc13f-152">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="bc13f-153">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bc13f-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="bc13f-154">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="bc13f-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="bc13f-155">Valore</span><span class="sxs-lookup"><span data-stu-id="bc13f-155">Value</span></span>|<span data-ttu-id="bc13f-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc13f-157">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bc13f-157">Enumeration</span></span>|<span data-ttu-id="bc13f-158">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="bc13f-159">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="bc13f-160">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="bc13f-161">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="bc13f-162">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc13f-163">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bc13f-163">Child Elements</span></span>  
 <span data-ttu-id="bc13f-164">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bc13f-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc13f-165">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bc13f-165">Parent Elements</span></span>  
  
|<span data-ttu-id="bc13f-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc13f-166">Element</span></span>|<span data-ttu-id="bc13f-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc13f-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc13f-168">\<peer ></span><span class="sxs-lookup"><span data-stu-id="bc13f-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="bc13f-169">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="bc13f-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc13f-170">Note</span><span class="sxs-lookup"><span data-stu-id="bc13f-170">Remarks</span></span>  
 <span data-ttu-id="bc13f-171">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="bc13f-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="bc13f-172">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dal [ \<certificato >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="bc13f-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="bc13f-173">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="bc13f-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="bc13f-174">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="bc13f-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc13f-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc13f-175">Example</span></span>  
 <span data-ttu-id="bc13f-176">Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="bc13f-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc13f-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc13f-177">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="bc13f-178">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="bc13f-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="bc13f-179">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="bc13f-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="bc13f-180">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="bc13f-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="bc13f-181">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="bc13f-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="bc13f-182">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="bc13f-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
