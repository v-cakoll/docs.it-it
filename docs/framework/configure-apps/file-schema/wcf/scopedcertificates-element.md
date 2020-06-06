---
title: <scopedCertificates> Elemento
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 3c06159709df0afe2a475de1e186b0114af32bc2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399961"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="ad4c2-102">\<scopedCertificates> Elemento</span><span class="sxs-lookup"><span data-stu-id="ad4c2-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="ad4c2-103">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="ad4c2-104">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="ad4c2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad4c2-105">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad4c2-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad4c2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ad4c2-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad4c2-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad4c2-108">Attributes</span></span>  
 <span data-ttu-id="ad4c2-109">No.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad4c2-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad4c2-110">Child Elements</span></span>  
  
|<span data-ttu-id="ad4c2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad4c2-111">Element</span></span>|<span data-ttu-id="ad4c2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c2-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="ad4c2-113">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-113">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad4c2-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad4c2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ad4c2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad4c2-115">Element</span></span>|<span data-ttu-id="ad4c2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c2-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="ad4c2-117">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-117">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad4c2-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="ad4c2-118">Remarks</span></span>  
 <span data-ttu-id="ad4c2-119">Questa raccolta consente al client di configurare i certificati del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-119">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="ad4c2-120">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="ad4c2-120">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="ad4c2-121">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-121">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="ad4c2-122">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-122">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="ad4c2-123">Per ulteriori informazioni, vedere la sezione "certificati con ambito" di [procedura: creare un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="ad4c2-123">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad4c2-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad4c2-124">Example</span></span>  
 <span data-ttu-id="ad4c2-125">Nell'esempio seguente viene specificato un certificato di servizio che il client deve utilizzare durante la comunicazione con gli endpoint il cui nome di dominio è `http://www.contoso.com` sul protocollo http.</span><span class="sxs-lookup"><span data-stu-id="ad4c2-125">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="ad4c2-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ad4c2-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="ad4c2-127">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="ad4c2-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ad4c2-128">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="ad4c2-128">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="ad4c2-129">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="ad4c2-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ad4c2-130">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="ad4c2-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
