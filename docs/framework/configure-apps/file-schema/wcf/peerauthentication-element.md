---
title: <peerAuthentication> Elemento
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400088"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="65185-102">\<peerAuthentication> Elemento</span><span class="sxs-lookup"><span data-stu-id="65185-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="65185-103">Specifica le opzioni di autenticazione dei client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="65185-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="65185-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="65185-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="65185-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65185-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65185-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="65185-106">Attributes and Elements</span></span>  
 <span data-ttu-id="65185-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="65185-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65185-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="65185-108">Attributes</span></span>  
  
|<span data-ttu-id="65185-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="65185-109">Attribute</span></span>|<span data-ttu-id="65185-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65185-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="65185-111">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="65185-111">Optional string.</span></span> <span data-ttu-id="65185-112">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="65185-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="65185-113">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="65185-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="65185-114">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="65185-114">Optional enumeration.</span></span> <span data-ttu-id="65185-115">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="65185-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="65185-116">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="65185-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="65185-117">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="65185-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="65185-118">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="65185-118">Optional enumeration.</span></span> <span data-ttu-id="65185-119">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="65185-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="65185-120">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="65185-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="65185-121">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="65185-121">Optional enumeration.</span></span> <span data-ttu-id="65185-122">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="65185-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="65185-123">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="65185-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="65185-124">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="65185-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="65185-125">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="65185-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="65185-126">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="65185-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="65185-127">Valore</span><span class="sxs-lookup"><span data-stu-id="65185-127">Value</span></span>|<span data-ttu-id="65185-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65185-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="65185-129">string</span><span class="sxs-lookup"><span data-stu-id="65185-129">String</span></span>|<span data-ttu-id="65185-130">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="65185-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="65185-131">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="65185-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="65185-132">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="65185-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="65185-133">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="65185-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="65185-134">Valore</span><span class="sxs-lookup"><span data-stu-id="65185-134">Value</span></span>|<span data-ttu-id="65185-135">Description</span><span class="sxs-lookup"><span data-stu-id="65185-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="65185-136">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="65185-136">Enumeration</span></span>|<span data-ttu-id="65185-137">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="65185-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="65185-138">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="65185-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="65185-139">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="65185-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="65185-140">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="65185-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="65185-141">Valore</span><span class="sxs-lookup"><span data-stu-id="65185-141">Value</span></span>|<span data-ttu-id="65185-142">Description</span><span class="sxs-lookup"><span data-stu-id="65185-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="65185-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="65185-143">Enumeration</span></span>|<span data-ttu-id="65185-144">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="65185-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="65185-145">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="65185-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="65185-146">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="65185-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="65185-147">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="65185-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="65185-148">Valore</span><span class="sxs-lookup"><span data-stu-id="65185-148">Value</span></span>|<span data-ttu-id="65185-149">Description</span><span class="sxs-lookup"><span data-stu-id="65185-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="65185-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="65185-150">Enumeration</span></span>|<span data-ttu-id="65185-151">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="65185-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="65185-152">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="65185-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="65185-153">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="65185-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="65185-154">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="65185-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65185-155">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="65185-155">Child Elements</span></span>  
 <span data-ttu-id="65185-156">No.</span><span class="sxs-lookup"><span data-stu-id="65185-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65185-157">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="65185-157">Parent Elements</span></span>  
  
|<span data-ttu-id="65185-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="65185-158">Element</span></span>|<span data-ttu-id="65185-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65185-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="65185-160">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="65185-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65185-161">Commenti</span><span class="sxs-lookup"><span data-stu-id="65185-161">Remarks</span></span>  
 <span data-ttu-id="65185-162">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="65185-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="65185-163">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="65185-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="65185-164">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="65185-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="65185-165">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="65185-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="65185-166">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="65185-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65185-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="65185-167">Example</span></span>  
 <span data-ttu-id="65185-168">Il codice seguente imposta la modalità di convalida del certificato su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="65185-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65185-169">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="65185-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="65185-170">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="65185-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="65185-171">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="65185-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="65185-172">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="65185-172">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="65185-173">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="65185-173">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="65185-174">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="65185-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
