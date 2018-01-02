---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1de8b8ceaf56931dfd3f09e5cc21ac939c49b4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="40e19-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="40e19-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="40e19-103">Specifica le impostazioni di autenticazione di un certificato peer usato da un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="40e19-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="40e19-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40e19-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="40e19-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="40e19-105">\<behaviors></span></span>  
<span data-ttu-id="40e19-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="40e19-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="40e19-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="40e19-107">\<behavior></span></span>  
<span data-ttu-id="40e19-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="40e19-108">\<serviceCredentials></span></span>  
<span data-ttu-id="40e19-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="40e19-109">\<peer></span></span>  
<span data-ttu-id="40e19-110">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="40e19-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e19-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40e19-111">Syntax</span></span>  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40e19-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="40e19-112">Attributes and Elements</span></span>  
 <span data-ttu-id="40e19-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="40e19-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40e19-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="40e19-114">Attributes</span></span>  
  
|<span data-ttu-id="40e19-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="40e19-115">Attribute</span></span>|<span data-ttu-id="40e19-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40e19-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="40e19-117">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="40e19-117">Optional enumeration.</span></span> <span data-ttu-id="40e19-118">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="40e19-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="40e19-119">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="40e19-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="40e19-120">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="40e19-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="40e19-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="40e19-121">Optional string.</span></span> <span data-ttu-id="40e19-122">Specifica un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="40e19-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="40e19-123">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="40e19-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="40e19-124">L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="40e19-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="40e19-125"> fornisce un validator del certificato peer predefinita che verifica il certificato peer a fronte dell'archivio Persone attendibili.</span><span class="sxs-lookup"><span data-stu-id="40e19-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="40e19-126">Verifica inoltre che il certificato sia concatenato a una radice valida.</span><span class="sxs-lookup"><span data-stu-id="40e19-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="40e19-127">È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="40e19-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="40e19-128">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="40e19-128">Optional enumeration.</span></span> <span data-ttu-id="40e19-129">Specifica la modalità di revoca dei certificati.</span><span class="sxs-lookup"><span data-stu-id="40e19-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="40e19-130">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="40e19-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="40e19-131">Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="40e19-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="40e19-132">Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="40e19-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="40e19-133">È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.</span><span class="sxs-lookup"><span data-stu-id="40e19-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="40e19-134">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="40e19-134">Optional enumeration.</span></span> <span data-ttu-id="40e19-135">Specifica il percorso dell'archivio dati attendibile in cui il certificato peer viene convalidato dal sistema di sicurezza [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40e19-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="40e19-136">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="40e19-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40e19-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="40e19-137">Child Elements</span></span>  
 <span data-ttu-id="40e19-138">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="40e19-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40e19-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="40e19-139">Parent Elements</span></span>  
  
|<span data-ttu-id="40e19-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="40e19-140">Element</span></span>|<span data-ttu-id="40e19-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40e19-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40e19-142">\<peer ></span><span class="sxs-lookup"><span data-stu-id="40e19-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="40e19-143">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="40e19-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40e19-144">Note</span><span class="sxs-lookup"><span data-stu-id="40e19-144">Remarks</span></span>  
 <span data-ttu-id="40e19-145">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="40e19-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="40e19-146">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="40e19-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="40e19-147">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="40e19-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="40e19-148">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="40e19-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="40e19-149">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="40e19-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e19-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40e19-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="40e19-151">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="40e19-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="40e19-152">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="40e19-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="40e19-153">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="40e19-153">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="40e19-154">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="40e19-154">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="40e19-155">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="40e19-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
