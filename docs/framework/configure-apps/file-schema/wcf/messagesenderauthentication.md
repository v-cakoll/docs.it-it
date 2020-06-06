---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398394"
---
# \<messageSenderAuthentication>
<span data-ttu-id="ccd4b-101">Specifica impostazioni di autenticazione per certificato peer usato dal mittente di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="ccd4b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccd4b-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccd4b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ccd4b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ccd4b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccd4b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ccd4b-105">Attributes</span></span>  
  
|<span data-ttu-id="ccd4b-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ccd4b-106">Attribute</span></span>|<span data-ttu-id="ccd4b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccd4b-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="ccd4b-108">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-108">Optional enumeration.</span></span> <span data-ttu-id="ccd4b-109">Specifica una delle cinque modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="ccd4b-110">L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="ccd4b-111">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="ccd4b-112">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-112">Optional string.</span></span> <span data-ttu-id="ccd4b-113">Specifica un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ccd4b-114">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="ccd4b-115">L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ccd4b-116">Windows Communication Foundation (WCF) fornisce un validator del certificato peer predefinito che verifica il certificato peer nell'archivio persone attendibili.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="ccd4b-117">Verifica inoltre che il certificato sia concatenato a una radice valida.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="ccd4b-118">È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="ccd4b-119">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-119">Optional enumeration.</span></span> <span data-ttu-id="ccd4b-120">Specifica la modalità di revoca dei certificati.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="ccd4b-121">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="ccd4b-122">Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="ccd4b-123">Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="ccd4b-124">È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ccd4b-125">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-125">Optional enumeration.</span></span> <span data-ttu-id="ccd4b-126">Specifica il percorso dell'archivio attendibile in cui il certificato peer viene convalidato dal sistema di sicurezza WCF.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="ccd4b-127">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccd4b-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ccd4b-128">Child Elements</span></span>  
 <span data-ttu-id="ccd4b-129">No.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccd4b-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ccd4b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ccd4b-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccd4b-131">Element</span></span>|<span data-ttu-id="ccd4b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccd4b-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="ccd4b-133">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccd4b-134">Commenti</span><span class="sxs-lookup"><span data-stu-id="ccd4b-134">Remarks</span></span>  
 <span data-ttu-id="ccd4b-135">Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="ccd4b-136">Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito da [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="ccd4b-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="ccd4b-137">Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="ccd4b-138">La convalida può accettare o rifiutare la credenziale.</span><span class="sxs-lookup"><span data-stu-id="ccd4b-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd4b-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ccd4b-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="ccd4b-140">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="ccd4b-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ccd4b-141">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ccd4b-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="ccd4b-142">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ccd4b-142">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ccd4b-143">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ccd4b-143">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ccd4b-144">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="ccd4b-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
