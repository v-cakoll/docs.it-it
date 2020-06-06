---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 118159617a7f4c27ecc5e8fe077c28cfefac8537
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397610"
---
# \<peerAuthentication>
<span data-ttu-id="10c07-101">Specifica le impostazioni di autenticazione di un certificato peer usato da un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="10c07-101">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="10c07-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10c07-102">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10c07-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="10c07-103">Attributes and Elements</span></span>  
 <span data-ttu-id="10c07-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="10c07-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10c07-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="10c07-105">Attributes</span></span>  
  
|<span data-ttu-id="10c07-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="10c07-106">Attribute</span></span>|<span data-ttu-id="10c07-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10c07-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="10c07-108">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="10c07-108">Optional enumeration.</span></span> <span data-ttu-id="10c07-109">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="10c07-109">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="10c07-110">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="10c07-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="10c07-111">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="10c07-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="10c07-112">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="10c07-112">Optional string.</span></span> <span data-ttu-id="10c07-113">Specifica un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="10c07-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="10c07-114">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="10c07-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="10c07-115">L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="10c07-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="10c07-116">Windows Communication Foundation (WCF) fornisce un validator del certificato peer predefinito che verifica il certificato peer nell'archivio persone attendibili.</span><span class="sxs-lookup"><span data-stu-id="10c07-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="10c07-117">Verifica inoltre che il certificato sia concatenato a una radice valida.</span><span class="sxs-lookup"><span data-stu-id="10c07-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="10c07-118">È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="10c07-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="10c07-119">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="10c07-119">Optional enumeration.</span></span> <span data-ttu-id="10c07-120">Specifica la modalità di revoca dei certificati.</span><span class="sxs-lookup"><span data-stu-id="10c07-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="10c07-121">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="10c07-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="10c07-122">Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="10c07-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="10c07-123">Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="10c07-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="10c07-124">È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.</span><span class="sxs-lookup"><span data-stu-id="10c07-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="10c07-125">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="10c07-125">Optional enumeration.</span></span> <span data-ttu-id="10c07-126">Specifica il percorso dell'archivio attendibile in cui il certificato peer viene convalidato dal sistema di sicurezza WCF.</span><span class="sxs-lookup"><span data-stu-id="10c07-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="10c07-127">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="10c07-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10c07-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="10c07-128">Child Elements</span></span>  
 <span data-ttu-id="10c07-129">No.</span><span class="sxs-lookup"><span data-stu-id="10c07-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10c07-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="10c07-130">Parent Elements</span></span>  
  
|<span data-ttu-id="10c07-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="10c07-131">Element</span></span>|<span data-ttu-id="10c07-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10c07-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="10c07-133">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="10c07-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10c07-134">Commenti</span><span class="sxs-lookup"><span data-stu-id="10c07-134">Remarks</span></span>  
 <span data-ttu-id="10c07-135">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="10c07-135">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="10c07-136">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="10c07-136">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="10c07-137">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="10c07-137">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="10c07-138">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="10c07-138">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="10c07-139">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="10c07-139">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c07-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="10c07-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="10c07-141">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="10c07-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="10c07-142">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="10c07-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="10c07-143">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="10c07-143">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="10c07-144">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="10c07-144">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="10c07-145">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="10c07-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
