---
title: <defaultCertificate> Elemento
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400420"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="6665f-102">\<Elemento > defaultCertificate</span><span class="sxs-lookup"><span data-stu-id="6665f-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="6665f-103">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="6665f-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="6665f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6665f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6665f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6665f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6665f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6665f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="6665f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="6665f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="6665f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> defaultCertificate**</span><span class="sxs-lookup"><span data-stu-id="6665f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6665f-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6665f-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6665f-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6665f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6665f-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6665f-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6665f-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="6665f-115">Attributes</span></span>  
  
|<span data-ttu-id="6665f-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="6665f-116">Attribute</span></span>|<span data-ttu-id="6665f-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6665f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6665f-118">findValue</span><span class="sxs-lookup"><span data-stu-id="6665f-118">findValue</span></span>|<span data-ttu-id="6665f-119">Stringa.</span><span class="sxs-lookup"><span data-stu-id="6665f-119">String.</span></span> <span data-ttu-id="6665f-120">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="6665f-120">The value to search for.</span></span>|  
|<span data-ttu-id="6665f-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="6665f-121">x509FindType</span></span>|<span data-ttu-id="6665f-122">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6665f-122">Enumeration.</span></span> <span data-ttu-id="6665f-123">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="6665f-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="6665f-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="6665f-124">storeLocation</span></span>|<span data-ttu-id="6665f-125">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6665f-125">Enumeration.</span></span> <span data-ttu-id="6665f-126">Uno di due percorsi dell'archivio di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="6665f-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="6665f-127">storeName</span><span class="sxs-lookup"><span data-stu-id="6665f-127">storeName</span></span>|<span data-ttu-id="6665f-128">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6665f-128">Enumeration.</span></span> <span data-ttu-id="6665f-129">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="6665f-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="6665f-130">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="6665f-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="6665f-131">Valore</span><span class="sxs-lookup"><span data-stu-id="6665f-131">Value</span></span>|<span data-ttu-id="6665f-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6665f-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6665f-133">String</span><span class="sxs-lookup"><span data-stu-id="6665f-133">String</span></span>|<span data-ttu-id="6665f-134">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="6665f-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="6665f-135">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="6665f-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="6665f-136">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="6665f-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="6665f-137">Value</span><span class="sxs-lookup"><span data-stu-id="6665f-137">Value</span></span>|<span data-ttu-id="6665f-138">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6665f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6665f-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="6665f-139">Enumeration</span></span>|<span data-ttu-id="6665f-140">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="6665f-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="6665f-141">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="6665f-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="6665f-142">Value</span><span class="sxs-lookup"><span data-stu-id="6665f-142">Value</span></span>|<span data-ttu-id="6665f-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6665f-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6665f-144">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="6665f-144">Enumeration</span></span>|<span data-ttu-id="6665f-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="6665f-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="6665f-146">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="6665f-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="6665f-147">Value</span><span class="sxs-lookup"><span data-stu-id="6665f-147">Value</span></span>|<span data-ttu-id="6665f-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6665f-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6665f-149">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="6665f-149">Enumeration</span></span>|<span data-ttu-id="6665f-150">I valori includono: AddressBook, AuthRoot, CertificateAuthority, non consentito, My, root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="6665f-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6665f-151">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6665f-151">Child Elements</span></span>  
 <span data-ttu-id="6665f-152">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6665f-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6665f-153">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6665f-153">Parent Elements</span></span>  
  
|<span data-ttu-id="6665f-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="6665f-154">Element</span></span>|<span data-ttu-id="6665f-155">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6665f-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6665f-156">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="6665f-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="6665f-157">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="6665f-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6665f-158">Note</span><span class="sxs-lookup"><span data-stu-id="6665f-158">Remarks</span></span>  
 <span data-ttu-id="6665f-159">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, il certificato specificato mediante questo elemento di configurazione viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="6665f-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="6665f-160">Può contenere un solo certificato da usare quando il servizio non specifica alcun certificato.</span><span class="sxs-lookup"><span data-stu-id="6665f-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6665f-161">Esempio</span><span class="sxs-lookup"><span data-stu-id="6665f-161">Example</span></span>  
 <span data-ttu-id="6665f-162">Nell'esempio seguente viene specificato un certificato da utilizzare per gli endpoint il cui URI `http://www.contoso.com` inizia con e un certificato da utilizzare per tutti gli altri endpoint che non eseguono la negoziazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="6665f-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="6665f-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6665f-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="6665f-164">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="6665f-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6665f-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="6665f-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="6665f-166">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="6665f-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="6665f-167">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="6665f-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
