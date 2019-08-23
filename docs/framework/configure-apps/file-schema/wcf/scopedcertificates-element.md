---
title: <scopedCertificates> Elemento
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: ed53a42575a8d57c365f7a329a1a9c1df075d6d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935226"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="8151e-102">\<Elemento > scopedCertificates</span><span class="sxs-lookup"><span data-stu-id="8151e-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="8151e-103">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8151e-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="8151e-104">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="8151e-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="8151e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8151e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8151e-106">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="8151e-106">\<behaviors></span></span>  
<span data-ttu-id="8151e-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="8151e-107">endpointBehaviors section</span></span>  
<span data-ttu-id="8151e-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8151e-108">\<behavior></span></span>  
<span data-ttu-id="8151e-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8151e-109">\<clientCredentials></span></span>  
<span data-ttu-id="8151e-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8151e-110">\<serviceCertificate></span></span>  
<span data-ttu-id="8151e-111">\<Elemento > scopedCertificates</span><span class="sxs-lookup"><span data-stu-id="8151e-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="8151e-112">\<aggiungere > elemento per \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="8151e-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8151e-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8151e-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8151e-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8151e-114">Attributes and Elements</span></span>  
 <span data-ttu-id="8151e-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8151e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8151e-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="8151e-116">Attributes</span></span>  
 <span data-ttu-id="8151e-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8151e-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8151e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8151e-118">Child Elements</span></span>  
  
|<span data-ttu-id="8151e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8151e-119">Element</span></span>|<span data-ttu-id="8151e-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8151e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8151e-121">\<add></span><span class="sxs-lookup"><span data-stu-id="8151e-121">\<add></span></span>](add-of-scopedcertificates-element.md)|<span data-ttu-id="8151e-122">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="8151e-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8151e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8151e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8151e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8151e-124">Element</span></span>|<span data-ttu-id="8151e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8151e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8151e-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8151e-126">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="8151e-127">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="8151e-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8151e-128">Note</span><span class="sxs-lookup"><span data-stu-id="8151e-128">Remarks</span></span>  
 <span data-ttu-id="8151e-129">Questa raccolta consente al client di configurare i certificati del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="8151e-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="8151e-130">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="8151e-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="8151e-131">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="8151e-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="8151e-132">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="8151e-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="8151e-133">Per ulteriori informazioni, vedere la sezione "certificati con ambito" di [procedura: Creare un client](../../../wcf/feature-details/how-to-create-a-federated-client.md)federato.</span><span class="sxs-lookup"><span data-stu-id="8151e-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8151e-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="8151e-134">Example</span></span>  
 <span data-ttu-id="8151e-135">Nell'esempio seguente viene specificato un certificato di servizio che il client deve utilizzare durante la comunicazione con gli endpoint il `http://www.contoso.com` cui nome di dominio è sul protocollo http.</span><span class="sxs-lookup"><span data-stu-id="8151e-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8151e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8151e-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="8151e-137">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="8151e-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8151e-138">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="8151e-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8151e-139">\<add></span><span class="sxs-lookup"><span data-stu-id="8151e-139">\<add></span></span>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="8151e-140">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="8151e-140">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8151e-141">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="8151e-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
