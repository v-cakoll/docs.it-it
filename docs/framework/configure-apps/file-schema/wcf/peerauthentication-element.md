---
title: <peerAuthentication> Elemento
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400088"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="70597-102">\<Elemento > peerAuthentication</span><span class="sxs-lookup"><span data-stu-id="70597-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="70597-103">Specifica le opzioni di autenticazione dei client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="70597-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="70597-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="70597-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="70597-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70597-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70597-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70597-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70597-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70597-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="70597-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70597-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="70597-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70597-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="70597-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="70597-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="70597-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peer**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="70597-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="70597-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> peerAuthentication**</span><span class="sxs-lookup"><span data-stu-id="70597-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70597-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70597-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70597-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="70597-114">Attributes and Elements</span></span>  
 <span data-ttu-id="70597-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="70597-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70597-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="70597-116">Attributes</span></span>  
  
|<span data-ttu-id="70597-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="70597-117">Attribute</span></span>|<span data-ttu-id="70597-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="70597-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="70597-119">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70597-119">Optional string.</span></span> <span data-ttu-id="70597-120">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="70597-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="70597-121">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="70597-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="70597-122">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70597-122">Optional enumeration.</span></span> <span data-ttu-id="70597-123">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="70597-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="70597-124">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="70597-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="70597-125">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="70597-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="70597-126">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70597-126">Optional enumeration.</span></span> <span data-ttu-id="70597-127">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="70597-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="70597-128">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="70597-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="70597-129">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70597-129">Optional enumeration.</span></span> <span data-ttu-id="70597-130">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="70597-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="70597-131">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="70597-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="70597-132">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="70597-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="70597-133">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="70597-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="70597-134">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="70597-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="70597-135">Value</span><span class="sxs-lookup"><span data-stu-id="70597-135">Value</span></span>|<span data-ttu-id="70597-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70597-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70597-137">String</span><span class="sxs-lookup"><span data-stu-id="70597-137">String</span></span>|<span data-ttu-id="70597-138">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="70597-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="70597-139">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="70597-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="70597-140">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="70597-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="70597-141">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="70597-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="70597-142">Value</span><span class="sxs-lookup"><span data-stu-id="70597-142">Value</span></span>|<span data-ttu-id="70597-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70597-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70597-144">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="70597-144">Enumeration</span></span>|<span data-ttu-id="70597-145">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="70597-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="70597-146">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="70597-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="70597-147">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="70597-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="70597-148">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="70597-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="70597-149">Value</span><span class="sxs-lookup"><span data-stu-id="70597-149">Value</span></span>|<span data-ttu-id="70597-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70597-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70597-151">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="70597-151">Enumeration</span></span>|<span data-ttu-id="70597-152">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="70597-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="70597-153">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="70597-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="70597-154">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="70597-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="70597-155">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="70597-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="70597-156">Value</span><span class="sxs-lookup"><span data-stu-id="70597-156">Value</span></span>|<span data-ttu-id="70597-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70597-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70597-158">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="70597-158">Enumeration</span></span>|<span data-ttu-id="70597-159">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="70597-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="70597-160">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="70597-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="70597-161">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="70597-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="70597-162">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="70597-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70597-163">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="70597-163">Child Elements</span></span>  
 <span data-ttu-id="70597-164">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="70597-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70597-165">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="70597-165">Parent Elements</span></span>  
  
|<span data-ttu-id="70597-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="70597-166">Element</span></span>|<span data-ttu-id="70597-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70597-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70597-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="70597-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="70597-169">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="70597-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70597-170">Note</span><span class="sxs-lookup"><span data-stu-id="70597-170">Remarks</span></span>  
 <span data-ttu-id="70597-171">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="70597-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="70597-172">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="70597-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="70597-173">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="70597-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="70597-174">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="70597-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="70597-175">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="70597-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70597-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="70597-176">Example</span></span>  
 <span data-ttu-id="70597-177">Il codice seguente imposta la modalità di convalida del certificato su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="70597-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="70597-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70597-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="70597-179">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="70597-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="70597-180">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="70597-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="70597-181">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70597-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="70597-182">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70597-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="70597-183">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="70597-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
