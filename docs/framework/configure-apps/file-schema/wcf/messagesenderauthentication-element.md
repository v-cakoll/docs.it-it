---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397780"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="33b25-102">\<elemento > messageSenderAuthentication</span><span class="sxs-lookup"><span data-stu-id="33b25-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="33b25-103">Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="33b25-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="33b25-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="33b25-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="33b25-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33b25-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33b25-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="33b25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="33b25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="33b25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="33b25-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peer**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="33b25-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="33b25-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> messageSenderAuthentication**</span><span class="sxs-lookup"><span data-stu-id="33b25-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b25-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33b25-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33b25-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33b25-114">Attributes and Elements</span></span>  
 <span data-ttu-id="33b25-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33b25-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33b25-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="33b25-116">Attributes</span></span>  
  
|<span data-ttu-id="33b25-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="33b25-117">Attribute</span></span>|<span data-ttu-id="33b25-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b25-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="33b25-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33b25-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="33b25-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="33b25-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="33b25-121">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="33b25-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="33b25-122">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="33b25-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="33b25-123">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="33b25-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="33b25-124">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33b25-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="33b25-125">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="33b25-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="33b25-126">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="33b25-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="33b25-127">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="33b25-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="33b25-128">Value</span><span class="sxs-lookup"><span data-stu-id="33b25-128">Value</span></span>|<span data-ttu-id="33b25-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33b25-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b25-130">String</span><span class="sxs-lookup"><span data-stu-id="33b25-130">String</span></span>|<span data-ttu-id="33b25-131">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="33b25-131">Optional.</span></span> <span data-ttu-id="33b25-132">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="33b25-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="33b25-133">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="33b25-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="33b25-134">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="33b25-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="33b25-135">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="33b25-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="33b25-136">Value</span><span class="sxs-lookup"><span data-stu-id="33b25-136">Value</span></span>|<span data-ttu-id="33b25-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b25-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b25-138">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="33b25-138">Enumeration</span></span>|<span data-ttu-id="33b25-139">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="33b25-139">Optional.</span></span> <span data-ttu-id="33b25-140">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="33b25-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="33b25-141">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="33b25-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="33b25-142">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="33b25-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="33b25-143">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="33b25-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="33b25-144">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="33b25-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="33b25-145">Value</span><span class="sxs-lookup"><span data-stu-id="33b25-145">Value</span></span>|<span data-ttu-id="33b25-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b25-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b25-147">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="33b25-147">Enumeration</span></span>|<span data-ttu-id="33b25-148">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="33b25-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="33b25-149">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="33b25-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="33b25-150">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="33b25-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="33b25-151">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="33b25-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="33b25-152">Valore</span><span class="sxs-lookup"><span data-stu-id="33b25-152">Value</span></span>|<span data-ttu-id="33b25-153">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33b25-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b25-154">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="33b25-154">Enumeration</span></span>|<span data-ttu-id="33b25-155">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33b25-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="33b25-156">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33b25-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="33b25-157">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="33b25-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="33b25-158">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33b25-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="33b25-159">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33b25-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33b25-160">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33b25-160">Child Elements</span></span>  
 <span data-ttu-id="33b25-161">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="33b25-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33b25-162">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33b25-162">Parent Elements</span></span>  
  
|<span data-ttu-id="33b25-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b25-163">Element</span></span>|<span data-ttu-id="33b25-164">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33b25-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b25-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="33b25-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="33b25-166">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="33b25-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33b25-167">Note</span><span class="sxs-lookup"><span data-stu-id="33b25-167">Remarks</span></span>  
 <span data-ttu-id="33b25-168">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="33b25-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="33b25-169">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dal [ \<certificato >](certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="33b25-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="33b25-170">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="33b25-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="33b25-171">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="33b25-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b25-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="33b25-172">Example</span></span>  
 <span data-ttu-id="33b25-173">Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="33b25-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33b25-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b25-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="33b25-175">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="33b25-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="33b25-176">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="33b25-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="33b25-177">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="33b25-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="33b25-178">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="33b25-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="33b25-179">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="33b25-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
