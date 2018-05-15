---
title: Elemento &lt;defaultCertificate&gt;
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: a4af1c6ec452b24634fa50162fa71f069e2451f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="51d65-102">Elemento &lt;defaultCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="51d65-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="51d65-103">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="51d65-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="51d65-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="51d65-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="51d65-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="51d65-105">\<behaviors></span></span>  
<span data-ttu-id="51d65-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="51d65-106">endpointBehaviors section</span></span>  
<span data-ttu-id="51d65-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="51d65-107">\<behavior></span></span>  
<span data-ttu-id="51d65-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="51d65-108">\<clientCredentials></span></span>  
<span data-ttu-id="51d65-109">\<elemento serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="51d65-109">\<serviceCertificate></span></span>  
<span data-ttu-id="51d65-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="51d65-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d65-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51d65-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51d65-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="51d65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="51d65-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="51d65-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51d65-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="51d65-114">Attributes</span></span>  
  
|<span data-ttu-id="51d65-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="51d65-115">Attribute</span></span>|<span data-ttu-id="51d65-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51d65-117">findValue</span><span class="sxs-lookup"><span data-stu-id="51d65-117">findValue</span></span>|<span data-ttu-id="51d65-118">Stringa.</span><span class="sxs-lookup"><span data-stu-id="51d65-118">String.</span></span> <span data-ttu-id="51d65-119">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="51d65-119">The value to search for.</span></span>|  
|<span data-ttu-id="51d65-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="51d65-120">x509FindType</span></span>|<span data-ttu-id="51d65-121">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51d65-121">Enumeration.</span></span> <span data-ttu-id="51d65-122">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="51d65-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="51d65-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="51d65-123">storeLocation</span></span>|<span data-ttu-id="51d65-124">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51d65-124">Enumeration.</span></span> <span data-ttu-id="51d65-125">Uno di due percorsi dell'archivio di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="51d65-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="51d65-126">storeName</span><span class="sxs-lookup"><span data-stu-id="51d65-126">storeName</span></span>|<span data-ttu-id="51d65-127">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51d65-127">Enumeration.</span></span> <span data-ttu-id="51d65-128">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="51d65-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="51d65-129">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="51d65-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="51d65-130">Valore</span><span class="sxs-lookup"><span data-stu-id="51d65-130">Value</span></span>|<span data-ttu-id="51d65-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51d65-132">String</span><span class="sxs-lookup"><span data-stu-id="51d65-132">String</span></span>|<span data-ttu-id="51d65-133">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="51d65-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="51d65-134">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="51d65-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="51d65-135">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="51d65-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="51d65-136">Valore</span><span class="sxs-lookup"><span data-stu-id="51d65-136">Value</span></span>|<span data-ttu-id="51d65-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51d65-138">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="51d65-138">Enumeration</span></span>|<span data-ttu-id="51d65-139">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="51d65-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="51d65-140">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="51d65-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="51d65-141">Valore</span><span class="sxs-lookup"><span data-stu-id="51d65-141">Value</span></span>|<span data-ttu-id="51d65-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51d65-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="51d65-143">Enumeration</span></span>|<span data-ttu-id="51d65-144">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="51d65-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="51d65-145">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="51d65-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="51d65-146">Valore</span><span class="sxs-lookup"><span data-stu-id="51d65-146">Value</span></span>|<span data-ttu-id="51d65-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51d65-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="51d65-148">Enumeration</span></span>|<span data-ttu-id="51d65-149">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="51d65-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51d65-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="51d65-150">Child Elements</span></span>  
 <span data-ttu-id="51d65-151">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="51d65-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51d65-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="51d65-152">Parent Elements</span></span>  
  
|<span data-ttu-id="51d65-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="51d65-153">Element</span></span>|<span data-ttu-id="51d65-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d65-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51d65-155">\<elemento serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="51d65-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="51d65-156">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="51d65-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51d65-157">Note</span><span class="sxs-lookup"><span data-stu-id="51d65-157">Remarks</span></span>  
 <span data-ttu-id="51d65-158">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, il certificato specificato mediante questo elemento di configurazione viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="51d65-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="51d65-159">Può contenere un solo certificato da usare quando il servizio non specifica alcun certificato.</span><span class="sxs-lookup"><span data-stu-id="51d65-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51d65-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="51d65-160">Example</span></span>  
 <span data-ttu-id="51d65-161">Nell'esempio seguente specifica un certificato da usare per endpoint il cui URI inizia con http://www.contoso.com e un certificato da usare per tutti gli altri endpoint che non eseguono negoziazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="51d65-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="51d65-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51d65-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="51d65-163">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="51d65-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="51d65-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="51d65-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="51d65-165">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="51d65-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="51d65-166">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="51d65-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
