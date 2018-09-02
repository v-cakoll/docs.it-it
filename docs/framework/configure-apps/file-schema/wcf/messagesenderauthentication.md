---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 8a3beb42d1064e6c6629014369628248b4cd5c8d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416014"
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="a224e-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="a224e-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="a224e-103">Specifica impostazioni di autenticazione per certificato peer usato dal mittente di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="a224e-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="a224e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a224e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a224e-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="a224e-105">\<behaviors></span></span>  
<span data-ttu-id="a224e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a224e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a224e-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a224e-107">\<behavior></span></span>  
<span data-ttu-id="a224e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a224e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a224e-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="a224e-109">\<peer></span></span>  
<span data-ttu-id="a224e-110">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="a224e-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a224e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a224e-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a224e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a224e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a224e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a224e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a224e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a224e-114">Attributes</span></span>  
  
|<span data-ttu-id="a224e-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="a224e-115">Attribute</span></span>|<span data-ttu-id="a224e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a224e-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="a224e-117">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a224e-117">Optional enumeration.</span></span> <span data-ttu-id="a224e-118">Specifica una delle cinque modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="a224e-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="a224e-119">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="a224e-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="a224e-120">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="a224e-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="a224e-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a224e-121">Optional string.</span></span> <span data-ttu-id="a224e-122">Specifica un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a224e-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a224e-123">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a224e-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="a224e-124">L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="a224e-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a224e-125">Windows Communication Foundation (WCF) offre un peer predefinito validator del certificato che verifica il certificato peer a fronte dell'archivio persone attendibili.</span><span class="sxs-lookup"><span data-stu-id="a224e-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="a224e-126">Verifica inoltre che il certificato sia concatenato a una radice valida.</span><span class="sxs-lookup"><span data-stu-id="a224e-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="a224e-127">È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a224e-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="a224e-128">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a224e-128">Optional enumeration.</span></span> <span data-ttu-id="a224e-129">Specifica la modalità di revoca dei certificati.</span><span class="sxs-lookup"><span data-stu-id="a224e-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="a224e-130">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="a224e-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="a224e-131">Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="a224e-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="a224e-132">Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="a224e-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="a224e-133">È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.</span><span class="sxs-lookup"><span data-stu-id="a224e-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a224e-134">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a224e-134">Optional enumeration.</span></span> <span data-ttu-id="a224e-135">Specifica il percorso di archivio dati attendibile dove il certificato peer viene convalidato dal sistema di sicurezza WCF.</span><span class="sxs-lookup"><span data-stu-id="a224e-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="a224e-136">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="a224e-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a224e-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a224e-137">Child Elements</span></span>  
 <span data-ttu-id="a224e-138">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a224e-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a224e-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a224e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a224e-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="a224e-140">Element</span></span>|<span data-ttu-id="a224e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a224e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a224e-142">\<peer ></span><span class="sxs-lookup"><span data-stu-id="a224e-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="a224e-143">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="a224e-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a224e-144">Note</span><span class="sxs-lookup"><span data-stu-id="a224e-144">Remarks</span></span>  
 <span data-ttu-id="a224e-145">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="a224e-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="a224e-146">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dalla [ \<certificato >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="a224e-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="a224e-147">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="a224e-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="a224e-148">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="a224e-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a224e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a224e-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="a224e-150">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="a224e-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a224e-151">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="a224e-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="a224e-152">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="a224e-152">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="a224e-153">Autenticazione personalizzata del canale peer</span><span class="sxs-lookup"><span data-stu-id="a224e-153">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="a224e-154">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="a224e-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
