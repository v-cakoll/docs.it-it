---
title: Elemento &lt;peerAuthentication&gt;
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9d8809378d8ad8bd5b62d6435919602e4ad0b042
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="3d5f5-102">Elemento &lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="3d5f5-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="3d5f5-103">Specifica le opzioni di autenticazione dei client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="3d5f5-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere [rete Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="3d5f5-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="3d5f5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d5f5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d5f5-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-106">\<behaviors></span></span>  
<span data-ttu-id="3d5f5-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="3d5f5-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-108">\<behavior></span></span>  
<span data-ttu-id="3d5f5-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3d5f5-109">\<clientCredentials></span></span>  
<span data-ttu-id="3d5f5-110">\<peer ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-110">\<peer></span></span>  
<span data-ttu-id="3d5f5-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5f5-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d5f5-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d5f5-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3d5f5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3d5f5-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d5f5-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d5f5-115">Attributes</span></span>  
  
|<span data-ttu-id="3d5f5-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="3d5f5-116">Attribute</span></span>|<span data-ttu-id="3d5f5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="3d5f5-118">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-118">Optional string.</span></span> <span data-ttu-id="3d5f5-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="3d5f5-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="3d5f5-121">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-121">Optional enumeration.</span></span> <span data-ttu-id="3d5f5-122">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="3d5f5-123">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="3d5f5-124">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="3d5f5-125">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-125">Optional enumeration.</span></span> <span data-ttu-id="3d5f5-126">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="3d5f5-127">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="3d5f5-128">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-128">Optional enumeration.</span></span> <span data-ttu-id="3d5f5-129">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="3d5f5-130">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="3d5f5-131">La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="3d5f5-132">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="3d5f5-133">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="3d5f5-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="3d5f5-134">Valore</span><span class="sxs-lookup"><span data-stu-id="3d5f5-134">Value</span></span>|<span data-ttu-id="3d5f5-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d5f5-136">String</span><span class="sxs-lookup"><span data-stu-id="3d5f5-136">String</span></span>|<span data-ttu-id="3d5f5-137">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="3d5f5-138">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="3d5f5-139">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="3d5f5-140">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3d5f5-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="3d5f5-141">Valore</span><span class="sxs-lookup"><span data-stu-id="3d5f5-141">Value</span></span>|<span data-ttu-id="3d5f5-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d5f5-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-143">Enumeration</span></span>|<span data-ttu-id="3d5f5-144">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="3d5f5-145">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="3d5f5-146">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3d5f5-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="3d5f5-147">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="3d5f5-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="3d5f5-148">Valore</span><span class="sxs-lookup"><span data-stu-id="3d5f5-148">Value</span></span>|<span data-ttu-id="3d5f5-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d5f5-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-150">Enumeration</span></span>|<span data-ttu-id="3d5f5-151">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="3d5f5-152">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="3d5f5-153">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="3d5f5-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="3d5f5-154">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3d5f5-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="3d5f5-155">Valore</span><span class="sxs-lookup"><span data-stu-id="3d5f5-155">Value</span></span>|<span data-ttu-id="3d5f5-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d5f5-157">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-157">Enumeration</span></span>|<span data-ttu-id="3d5f5-158">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="3d5f5-159">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="3d5f5-160">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="3d5f5-161">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d5f5-162">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d5f5-162">Child Elements</span></span>  
 <span data-ttu-id="3d5f5-163">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d5f5-164">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3d5f5-164">Parent Elements</span></span>  
  
|<span data-ttu-id="3d5f5-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d5f5-165">Element</span></span>|<span data-ttu-id="3d5f5-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5f5-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d5f5-167">\<peer ></span><span class="sxs-lookup"><span data-stu-id="3d5f5-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="3d5f5-168">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d5f5-169">Note</span><span class="sxs-lookup"><span data-stu-id="3d5f5-169">Remarks</span></span>  
 <span data-ttu-id="3d5f5-170">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="3d5f5-171">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="3d5f5-172">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="3d5f5-173">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="3d5f5-174">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d5f5-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d5f5-175">Example</span></span>  
 <span data-ttu-id="3d5f5-176">Il codice seguente imposta la modalità di convalida del certificato su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d5f5-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d5f5-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="3d5f5-178">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="3d5f5-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="3d5f5-179">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="3d5f5-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="3d5f5-180">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="3d5f5-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="3d5f5-181">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="3d5f5-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="3d5f5-182">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="3d5f5-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
