---
title: Elemento &lt;scopedCertificates&gt;
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 6f2acd1078090f7680f1909d68afbcaa09d080fd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150721"
---
# <a name="ltscopedcertificatesgt-element"></a><span data-ttu-id="414d2-102">Elemento &lt;scopedCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="414d2-102">&lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="414d2-103">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="414d2-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="414d2-104">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="414d2-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="414d2-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="414d2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="414d2-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="414d2-106">\<behaviors></span></span>  
<span data-ttu-id="414d2-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="414d2-107">endpointBehaviors section</span></span>  
<span data-ttu-id="414d2-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="414d2-108">\<behavior></span></span>  
<span data-ttu-id="414d2-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="414d2-109">\<clientCredentials></span></span>  
<span data-ttu-id="414d2-110">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="414d2-110">\<serviceCertificate></span></span>  
<span data-ttu-id="414d2-111">\<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="414d2-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="414d2-112">\<aggiungere > (elemento) per \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="414d2-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="414d2-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="414d2-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="414d2-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="414d2-114">Attributes and Elements</span></span>  
 <span data-ttu-id="414d2-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="414d2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="414d2-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="414d2-116">Attributes</span></span>  
 <span data-ttu-id="414d2-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="414d2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="414d2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="414d2-118">Child Elements</span></span>  
  
|<span data-ttu-id="414d2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="414d2-119">Element</span></span>|<span data-ttu-id="414d2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="414d2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="414d2-121">\<add></span><span class="sxs-lookup"><span data-stu-id="414d2-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="414d2-122">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="414d2-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="414d2-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="414d2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="414d2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="414d2-124">Element</span></span>|<span data-ttu-id="414d2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="414d2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="414d2-126">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="414d2-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="414d2-127">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="414d2-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="414d2-128">Note</span><span class="sxs-lookup"><span data-stu-id="414d2-128">Remarks</span></span>  
 <span data-ttu-id="414d2-129">Questa raccolta consente al client di configurare i certificati del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="414d2-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="414d2-130">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="414d2-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="414d2-131">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="414d2-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="414d2-132">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="414d2-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="414d2-133">Per altre informazioni, vedere la sezione "Scoped Certificates" di [come: Creare un Client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="414d2-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="414d2-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="414d2-134">Example</span></span>  
 <span data-ttu-id="414d2-135">L'esempio seguente specifica un certificato di servizio per il client da utilizzare per comunicare con endpoint il cui nome di dominio è `http://www.contoso.com` sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="414d2-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="414d2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="414d2-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="414d2-137">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="414d2-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="414d2-138">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="414d2-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="414d2-139">\<add></span><span class="sxs-lookup"><span data-stu-id="414d2-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [<span data-ttu-id="414d2-140">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="414d2-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="414d2-141">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="414d2-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
