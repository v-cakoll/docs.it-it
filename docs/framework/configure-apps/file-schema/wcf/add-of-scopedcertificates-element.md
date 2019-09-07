---
title: <add>dell' <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398337"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="99b9b-102">\<Aggiungi > dell' \<elemento > scopedCertificates</span><span class="sxs-lookup"><span data-stu-id="99b9b-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="99b9b-103">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="99b9b-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="99b9b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99b9b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99b9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="99b9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="99b9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="99b9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="99b9b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="99b9b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> scopedCertificates**](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="99b9b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="99b9b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="99b9b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b9b-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99b9b-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99b9b-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99b9b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="99b9b-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99b9b-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99b9b-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="99b9b-116">Attributes</span></span>  
  
|<span data-ttu-id="99b9b-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="99b9b-117">Attribute</span></span>|<span data-ttu-id="99b9b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b9b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99b9b-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="99b9b-119">targetUri</span></span>|<span data-ttu-id="99b9b-120">Stringa.</span><span class="sxs-lookup"><span data-stu-id="99b9b-120">String.</span></span> <span data-ttu-id="99b9b-121">Specifica l'URI del servizio associato al certificato.</span><span class="sxs-lookup"><span data-stu-id="99b9b-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="99b9b-122">findValue</span><span class="sxs-lookup"><span data-stu-id="99b9b-122">findValue</span></span>|<span data-ttu-id="99b9b-123">Stringa.</span><span class="sxs-lookup"><span data-stu-id="99b9b-123">String.</span></span> <span data-ttu-id="99b9b-124">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="99b9b-124">The value to search for.</span></span>|  
|<span data-ttu-id="99b9b-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="99b9b-125">x509FindType</span></span>|<span data-ttu-id="99b9b-126">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="99b9b-126">Enumeration.</span></span> <span data-ttu-id="99b9b-127">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="99b9b-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="99b9b-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="99b9b-128">storeLocation</span></span>|<span data-ttu-id="99b9b-129">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="99b9b-129">Enumeration.</span></span> <span data-ttu-id="99b9b-130">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="99b9b-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="99b9b-131">storeName</span><span class="sxs-lookup"><span data-stu-id="99b9b-131">storeName</span></span>|<span data-ttu-id="99b9b-132">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="99b9b-132">Enumeration.</span></span> <span data-ttu-id="99b9b-133">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="99b9b-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="99b9b-134">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="99b9b-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="99b9b-135">Valore</span><span class="sxs-lookup"><span data-stu-id="99b9b-135">Value</span></span>|<span data-ttu-id="99b9b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b9b-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99b9b-137">String</span><span class="sxs-lookup"><span data-stu-id="99b9b-137">String</span></span>|<span data-ttu-id="99b9b-138">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="99b9b-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="99b9b-139">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="99b9b-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="99b9b-140">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="99b9b-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="99b9b-141">Value</span><span class="sxs-lookup"><span data-stu-id="99b9b-141">Value</span></span>|<span data-ttu-id="99b9b-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b9b-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99b9b-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="99b9b-143">Enumeration</span></span>|<span data-ttu-id="99b9b-144">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="99b9b-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="99b9b-145">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="99b9b-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="99b9b-146">Valore</span><span class="sxs-lookup"><span data-stu-id="99b9b-146">Value</span></span>|<span data-ttu-id="99b9b-147">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="99b9b-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99b9b-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="99b9b-148">Enumeration</span></span>|<span data-ttu-id="99b9b-149">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="99b9b-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="99b9b-150">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="99b9b-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="99b9b-151">Value</span><span class="sxs-lookup"><span data-stu-id="99b9b-151">Value</span></span>|<span data-ttu-id="99b9b-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b9b-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99b9b-153">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="99b9b-153">Enumeration</span></span>|<span data-ttu-id="99b9b-154">I valori includono: AddressBook, AuthRoot, CertificateAuthority, non consentito, My, root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="99b9b-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99b9b-155">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99b9b-155">Child Elements</span></span>  
 <span data-ttu-id="99b9b-156">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="99b9b-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99b9b-157">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99b9b-157">Parent Elements</span></span>  
  
|<span data-ttu-id="99b9b-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="99b9b-158">Element</span></span>|<span data-ttu-id="99b9b-159">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="99b9b-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99b9b-160">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="99b9b-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="99b9b-161">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="99b9b-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99b9b-162">Note</span><span class="sxs-lookup"><span data-stu-id="99b9b-162">Remarks</span></span>  
 <span data-ttu-id="99b9b-163">Questo elemento consente al client di configurare un certificato del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="99b9b-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="99b9b-164">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="99b9b-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="99b9b-165">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="99b9b-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="99b9b-166">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="99b9b-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="99b9b-167">Per ulteriori informazioni, vedere la sezione "certificati con ambito" di [procedura: Creare un client](../../../wcf/feature-details/how-to-create-a-federated-client.md)federato.</span><span class="sxs-lookup"><span data-stu-id="99b9b-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b9b-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="99b9b-168">Example</span></span>  
 <span data-ttu-id="99b9b-169">Nell'esempio seguente un certificato X.509 viene aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="99b9b-169">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99b9b-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99b9b-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="99b9b-171">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="99b9b-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="99b9b-172">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="99b9b-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="99b9b-173">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="99b9b-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="99b9b-174">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="99b9b-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
