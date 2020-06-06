---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397780"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="2b370-102">Elemento \<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="2b370-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="2b370-103">Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="2b370-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="2b370-104">Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="2b370-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="2b370-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b370-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b370-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b370-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2b370-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b370-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b370-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b370-108">Attributes</span></span>  
  
|<span data-ttu-id="2b370-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="2b370-109">Attribute</span></span>|<span data-ttu-id="2b370-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b370-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="2b370-111">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2b370-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="2b370-112">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2b370-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="2b370-113">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="2b370-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="2b370-114">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="2b370-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="2b370-115">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="2b370-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="2b370-116">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2b370-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2b370-117">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="2b370-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2b370-118">La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.</span><span class="sxs-lookup"><span data-stu-id="2b370-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="2b370-119">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2b370-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="2b370-120">Valore</span><span class="sxs-lookup"><span data-stu-id="2b370-120">Value</span></span>|<span data-ttu-id="2b370-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b370-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b370-122">string</span><span class="sxs-lookup"><span data-stu-id="2b370-122">String</span></span>|<span data-ttu-id="2b370-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2b370-123">Optional.</span></span> <span data-ttu-id="2b370-124">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="2b370-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="2b370-125">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="2b370-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="2b370-126">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="2b370-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2b370-127">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2b370-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2b370-128">Valore</span><span class="sxs-lookup"><span data-stu-id="2b370-128">Value</span></span>|<span data-ttu-id="2b370-129">Description</span><span class="sxs-lookup"><span data-stu-id="2b370-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b370-130">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2b370-130">Enumeration</span></span>|<span data-ttu-id="2b370-131">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="2b370-131">Optional.</span></span> <span data-ttu-id="2b370-132">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2b370-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="2b370-133">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2b370-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="2b370-134">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2b370-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="2b370-135">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2b370-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2b370-136">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="2b370-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2b370-137">Valore</span><span class="sxs-lookup"><span data-stu-id="2b370-137">Value</span></span>|<span data-ttu-id="2b370-138">Description</span><span class="sxs-lookup"><span data-stu-id="2b370-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b370-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2b370-139">Enumeration</span></span>|<span data-ttu-id="2b370-140">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="2b370-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="2b370-141">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="2b370-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="2b370-142">Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2b370-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2b370-143">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2b370-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2b370-144">Valore</span><span class="sxs-lookup"><span data-stu-id="2b370-144">Value</span></span>|<span data-ttu-id="2b370-145">Description</span><span class="sxs-lookup"><span data-stu-id="2b370-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b370-146">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="2b370-146">Enumeration</span></span>|<span data-ttu-id="2b370-147">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2b370-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2b370-148">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2b370-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="2b370-149">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="2b370-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="2b370-150">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2b370-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="2b370-151">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2b370-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b370-152">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b370-152">Child Elements</span></span>  
 <span data-ttu-id="2b370-153">No.</span><span class="sxs-lookup"><span data-stu-id="2b370-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b370-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b370-154">Parent Elements</span></span>  
  
|<span data-ttu-id="2b370-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b370-155">Element</span></span>|<span data-ttu-id="2b370-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b370-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="2b370-157">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="2b370-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b370-158">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b370-158">Remarks</span></span>  
 <span data-ttu-id="2b370-159">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2b370-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="2b370-160">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito da [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="2b370-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="2b370-161">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2b370-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="2b370-162">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="2b370-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b370-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b370-163">Example</span></span>  
 <span data-ttu-id="2b370-164">Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2b370-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b370-165">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2b370-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="2b370-166">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="2b370-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2b370-167">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="2b370-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="2b370-168">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2b370-168">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="2b370-169">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2b370-169">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="2b370-170">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="2b370-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
