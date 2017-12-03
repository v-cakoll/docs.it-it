---
title: Elemento &lt;defaultCertificate&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aae72b7ae006a57683ea0e274fbc072c7f69cfb1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="22d98-102">Elemento &lt;defaultCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="22d98-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="22d98-103">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="22d98-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="22d98-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="22d98-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22d98-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="22d98-105">\<behaviors></span></span>  
<span data-ttu-id="22d98-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="22d98-106">endpointBehaviors section</span></span>  
<span data-ttu-id="22d98-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="22d98-107">\<behavior></span></span>  
<span data-ttu-id="22d98-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="22d98-108">\<clientCredentials></span></span>  
<span data-ttu-id="22d98-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="22d98-109">\<serviceCertificate></span></span>  
<span data-ttu-id="22d98-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="22d98-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d98-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22d98-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22d98-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22d98-112">Attributes and Elements</span></span>  
 <span data-ttu-id="22d98-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22d98-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22d98-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="22d98-114">Attributes</span></span>  
  
|<span data-ttu-id="22d98-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="22d98-115">Attribute</span></span>|<span data-ttu-id="22d98-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22d98-117">findValue</span><span class="sxs-lookup"><span data-stu-id="22d98-117">findValue</span></span>|<span data-ttu-id="22d98-118">Stringa.</span><span class="sxs-lookup"><span data-stu-id="22d98-118">String.</span></span> <span data-ttu-id="22d98-119">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="22d98-119">The value to search for.</span></span>|  
|<span data-ttu-id="22d98-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="22d98-120">x509FindType</span></span>|<span data-ttu-id="22d98-121">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="22d98-121">Enumeration.</span></span> <span data-ttu-id="22d98-122">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="22d98-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="22d98-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="22d98-123">storeLocation</span></span>|<span data-ttu-id="22d98-124">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="22d98-124">Enumeration.</span></span> <span data-ttu-id="22d98-125">Uno di due percorsi dell'archivio di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="22d98-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="22d98-126">storeName</span><span class="sxs-lookup"><span data-stu-id="22d98-126">storeName</span></span>|<span data-ttu-id="22d98-127">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="22d98-127">Enumeration.</span></span> <span data-ttu-id="22d98-128">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="22d98-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="22d98-129">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="22d98-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="22d98-130">Valore</span><span class="sxs-lookup"><span data-stu-id="22d98-130">Value</span></span>|<span data-ttu-id="22d98-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22d98-132">String</span><span class="sxs-lookup"><span data-stu-id="22d98-132">String</span></span>|<span data-ttu-id="22d98-133">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="22d98-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="22d98-134">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="22d98-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="22d98-135">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="22d98-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="22d98-136">Valore</span><span class="sxs-lookup"><span data-stu-id="22d98-136">Value</span></span>|<span data-ttu-id="22d98-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22d98-138">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="22d98-138">Enumeration</span></span>|<span data-ttu-id="22d98-139">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="22d98-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="22d98-140">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="22d98-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="22d98-141">Valore</span><span class="sxs-lookup"><span data-stu-id="22d98-141">Value</span></span>|<span data-ttu-id="22d98-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22d98-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="22d98-143">Enumeration</span></span>|<span data-ttu-id="22d98-144">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="22d98-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="22d98-145">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="22d98-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="22d98-146">Valore</span><span class="sxs-lookup"><span data-stu-id="22d98-146">Value</span></span>|<span data-ttu-id="22d98-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22d98-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="22d98-148">Enumeration</span></span>|<span data-ttu-id="22d98-149">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="22d98-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22d98-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22d98-150">Child Elements</span></span>  
 <span data-ttu-id="22d98-151">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="22d98-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22d98-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22d98-152">Parent Elements</span></span>  
  
|<span data-ttu-id="22d98-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="22d98-153">Element</span></span>|<span data-ttu-id="22d98-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d98-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22d98-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="22d98-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="22d98-156">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="22d98-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d98-157">Note</span><span class="sxs-lookup"><span data-stu-id="22d98-157">Remarks</span></span>  
 <span data-ttu-id="22d98-158">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, il certificato specificato mediante questo elemento di configurazione viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="22d98-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="22d98-159">Può contenere un solo certificato da usare quando il servizio non specifica alcun certificato.</span><span class="sxs-lookup"><span data-stu-id="22d98-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d98-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="22d98-160">Example</span></span>  
 <span data-ttu-id="22d98-161">Nell'esempio seguente viene specificato un certificato da usare per endpoint il cui URI inizia con http://www.contoso.com e un certificato da usare per tutti gli altri endpoint che non eseguono negoziazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="22d98-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22d98-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d98-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="22d98-163">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="22d98-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="22d98-164">\<autenticazione ></span><span class="sxs-lookup"><span data-stu-id="22d98-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="22d98-165">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="22d98-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="22d98-166">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="22d98-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
