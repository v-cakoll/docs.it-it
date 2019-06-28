---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 804c280bcdb0fecc87f71121b7d95b5fd0268de9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423116"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="2158d-102">\<messageSenderAuthentication > elemento</span><span class="sxs-lookup"><span data-stu-id="2158d-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="2158d-103">Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="2158d-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="2158d-104">Per altre informazioni sulla programmazione peer-to-peer, vedere [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="2158d-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="2158d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2158d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2158d-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2158d-106">\<behaviors></span></span>  
<span data-ttu-id="2158d-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2158d-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="2158d-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2158d-108">\<behavior></span></span>  
<span data-ttu-id="2158d-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2158d-109">\<clientCredentials></span></span>  
<span data-ttu-id="2158d-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="2158d-110">\<peer></span></span>  
<span data-ttu-id="2158d-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="2158d-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2158d-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2158d-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2158d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2158d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2158d-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2158d-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2158d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="2158d-115">Attributes</span></span>  
  
|<span data-ttu-id="2158d-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="2158d-116">Attribute</span></span>|<span data-ttu-id="2158d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="2158d-118">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2158d-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="2158d-119">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2158d-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="2158d-120">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="2158d-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="2158d-121">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="2158d-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="2158d-122">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="2158d-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="2158d-123">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2158d-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2158d-124">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="2158d-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2158d-125">La convalida viene eseguita sul **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="2158d-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="2158d-126">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2158d-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="2158d-127">Value</span><span class="sxs-lookup"><span data-stu-id="2158d-127">Value</span></span>|<span data-ttu-id="2158d-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2158d-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="2158d-129">String</span></span>|<span data-ttu-id="2158d-130">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2158d-130">Optional.</span></span> <span data-ttu-id="2158d-131">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="2158d-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="2158d-132">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="2158d-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="2158d-133">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="2158d-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2158d-134">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2158d-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2158d-135">Value</span><span class="sxs-lookup"><span data-stu-id="2158d-135">Value</span></span>|<span data-ttu-id="2158d-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2158d-137">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2158d-137">Enumeration</span></span>|<span data-ttu-id="2158d-138">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2158d-138">Optional.</span></span> <span data-ttu-id="2158d-139">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2158d-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="2158d-140">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2158d-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="2158d-141">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2158d-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="2158d-142">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2158d-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2158d-143">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="2158d-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2158d-144">Value</span><span class="sxs-lookup"><span data-stu-id="2158d-144">Value</span></span>|<span data-ttu-id="2158d-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2158d-146">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2158d-146">Enumeration</span></span>|<span data-ttu-id="2158d-147">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="2158d-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="2158d-148">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="2158d-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="2158d-149">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2158d-149">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2158d-150">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2158d-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2158d-151">Value</span><span class="sxs-lookup"><span data-stu-id="2158d-151">Value</span></span>|<span data-ttu-id="2158d-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2158d-153">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2158d-153">Enumeration</span></span>|<span data-ttu-id="2158d-154">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2158d-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2158d-155">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2158d-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="2158d-156">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="2158d-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="2158d-157">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2158d-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="2158d-158">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2158d-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2158d-159">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2158d-159">Child Elements</span></span>  
 <span data-ttu-id="2158d-160">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2158d-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2158d-161">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2158d-161">Parent Elements</span></span>  
  
|<span data-ttu-id="2158d-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="2158d-162">Element</span></span>|<span data-ttu-id="2158d-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2158d-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2158d-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="2158d-164">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="2158d-165">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="2158d-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2158d-166">Note</span><span class="sxs-lookup"><span data-stu-id="2158d-166">Remarks</span></span>  
 <span data-ttu-id="2158d-167">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2158d-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="2158d-168">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dalla [ \<certificato >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="2158d-168">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="2158d-169">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2158d-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="2158d-170">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="2158d-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2158d-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="2158d-171">Example</span></span>  
 <span data-ttu-id="2158d-172">Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2158d-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="2158d-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2158d-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="2158d-174">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="2158d-174">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2158d-175">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="2158d-175">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="2158d-176">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2158d-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="2158d-177">[Autenticazione personalizzata del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2158d-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="2158d-178">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="2158d-178">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
