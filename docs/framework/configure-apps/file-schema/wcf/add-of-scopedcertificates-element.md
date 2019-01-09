---
title: Elemento &lt;add&gt; di &lt;scopedCertificates&gt;
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: a173d3b137833abfe8a69aed55b972c9b6469890
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146095"
---
# <a name="ltaddgt-of-ltscopedcertificatesgt-element"></a><span data-ttu-id="0f5ac-102">Elemento &lt;add&gt; di &lt;scopedCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="0f5ac-102">&lt;add&gt; of &lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="0f5ac-103">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="0f5ac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0f5ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f5ac-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-105">\<behaviors></span></span>  
<span data-ttu-id="0f5ac-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="0f5ac-106">endpointBehaviors section</span></span>  
<span data-ttu-id="0f5ac-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-107">\<behavior></span></span>  
<span data-ttu-id="0f5ac-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0f5ac-108">\<clientCredentials></span></span>  
<span data-ttu-id="0f5ac-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-109">\<serviceCertificate></span></span>  
<span data-ttu-id="0f5ac-110">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-110">\<scopedCertificates></span></span>  
<span data-ttu-id="0f5ac-111">\<aggiungere > (elemento) per \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f5ac-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f5ac-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f5ac-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0f5ac-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0f5ac-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f5ac-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="0f5ac-115">Attributes</span></span>  
  
|<span data-ttu-id="0f5ac-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="0f5ac-116">Attribute</span></span>|<span data-ttu-id="0f5ac-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f5ac-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="0f5ac-118">targetUri</span></span>|<span data-ttu-id="0f5ac-119">Stringa.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-119">String.</span></span> <span data-ttu-id="0f5ac-120">Specifica l'URI del servizio associato al certificato.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="0f5ac-121">findValue</span><span class="sxs-lookup"><span data-stu-id="0f5ac-121">findValue</span></span>|<span data-ttu-id="0f5ac-122">Stringa.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-122">String.</span></span> <span data-ttu-id="0f5ac-123">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-123">The value to search for.</span></span>|  
|<span data-ttu-id="0f5ac-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0f5ac-124">x509FindType</span></span>|<span data-ttu-id="0f5ac-125">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-125">Enumeration.</span></span> <span data-ttu-id="0f5ac-126">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="0f5ac-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0f5ac-127">storeLocation</span></span>|<span data-ttu-id="0f5ac-128">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-128">Enumeration.</span></span> <span data-ttu-id="0f5ac-129">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="0f5ac-130">storeName</span><span class="sxs-lookup"><span data-stu-id="0f5ac-130">storeName</span></span>|<span data-ttu-id="0f5ac-131">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-131">Enumeration.</span></span> <span data-ttu-id="0f5ac-132">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="0f5ac-133">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="0f5ac-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="0f5ac-134">Valore</span><span class="sxs-lookup"><span data-stu-id="0f5ac-134">Value</span></span>|<span data-ttu-id="0f5ac-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f5ac-136">String</span><span class="sxs-lookup"><span data-stu-id="0f5ac-136">String</span></span>|<span data-ttu-id="0f5ac-137">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="0f5ac-138">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="0f5ac-139">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="0f5ac-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="0f5ac-140">Valore</span><span class="sxs-lookup"><span data-stu-id="0f5ac-140">Value</span></span>|<span data-ttu-id="0f5ac-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f5ac-142">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-142">Enumeration</span></span>|<span data-ttu-id="0f5ac-143">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="0f5ac-144">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="0f5ac-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="0f5ac-145">Valore</span><span class="sxs-lookup"><span data-stu-id="0f5ac-145">Value</span></span>|<span data-ttu-id="0f5ac-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f5ac-147">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-147">Enumeration</span></span>|<span data-ttu-id="0f5ac-148">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="0f5ac-149">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="0f5ac-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="0f5ac-150">Valore</span><span class="sxs-lookup"><span data-stu-id="0f5ac-150">Value</span></span>|<span data-ttu-id="0f5ac-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f5ac-152">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-152">Enumeration</span></span>|<span data-ttu-id="0f5ac-153">I valori includono: AddressBook, AuthRoot, CertificateAuthority, disattivati, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f5ac-154">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0f5ac-154">Child Elements</span></span>  
 <span data-ttu-id="0f5ac-155">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f5ac-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0f5ac-156">Parent Elements</span></span>  
  
|<span data-ttu-id="0f5ac-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f5ac-157">Element</span></span>|<span data-ttu-id="0f5ac-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f5ac-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f5ac-159">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="0f5ac-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="0f5ac-160">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f5ac-161">Note</span><span class="sxs-lookup"><span data-stu-id="0f5ac-161">Remarks</span></span>  
 <span data-ttu-id="0f5ac-162">Questo elemento consente al client di configurare un certificato del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="0f5ac-163">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="0f5ac-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="0f5ac-164">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="0f5ac-165">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="0f5ac-166">Per altre informazioni, vedere la sezione "Scoped Certificates" di [come: Creare un Client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="0f5ac-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f5ac-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f5ac-167">Example</span></span>  
 <span data-ttu-id="0f5ac-168">Nell'esempio seguente un certificato X.509 viene aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="0f5ac-168">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="0f5ac-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f5ac-169">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="0f5ac-170">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="0f5ac-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="0f5ac-171">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="0f5ac-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="0f5ac-172">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="0f5ac-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0f5ac-173">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="0f5ac-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
