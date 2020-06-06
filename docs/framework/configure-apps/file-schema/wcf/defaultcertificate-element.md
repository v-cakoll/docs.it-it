---
title: <defaultCertificate> Elemento
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400420"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="ddc35-102">\<defaultCertificate> Elemento</span><span class="sxs-lookup"><span data-stu-id="ddc35-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="ddc35-103">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="ddc35-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ddc35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddc35-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddc35-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ddc35-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ddc35-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ddc35-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddc35-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ddc35-107">Attributes</span></span>  
  
|<span data-ttu-id="ddc35-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ddc35-108">Attribute</span></span>|<span data-ttu-id="ddc35-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddc35-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddc35-110">findValue</span><span class="sxs-lookup"><span data-stu-id="ddc35-110">findValue</span></span>|<span data-ttu-id="ddc35-111">Stringa.</span><span class="sxs-lookup"><span data-stu-id="ddc35-111">String.</span></span> <span data-ttu-id="ddc35-112">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="ddc35-112">The value to search for.</span></span>|  
|<span data-ttu-id="ddc35-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ddc35-113">x509FindType</span></span>|<span data-ttu-id="ddc35-114">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ddc35-114">Enumeration.</span></span> <span data-ttu-id="ddc35-115">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="ddc35-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="ddc35-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ddc35-116">storeLocation</span></span>|<span data-ttu-id="ddc35-117">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ddc35-117">Enumeration.</span></span> <span data-ttu-id="ddc35-118">Uno di due percorsi dell'archivio di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="ddc35-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="ddc35-119">storeName</span><span class="sxs-lookup"><span data-stu-id="ddc35-119">storeName</span></span>|<span data-ttu-id="ddc35-120">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ddc35-120">Enumeration.</span></span> <span data-ttu-id="ddc35-121">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="ddc35-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ddc35-122">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="ddc35-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="ddc35-123">Valore</span><span class="sxs-lookup"><span data-stu-id="ddc35-123">Value</span></span>|<span data-ttu-id="ddc35-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddc35-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ddc35-125">string</span><span class="sxs-lookup"><span data-stu-id="ddc35-125">String</span></span>|<span data-ttu-id="ddc35-126">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="ddc35-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ddc35-127">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="ddc35-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ddc35-128">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="ddc35-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ddc35-129">Valore</span><span class="sxs-lookup"><span data-stu-id="ddc35-129">Value</span></span>|<span data-ttu-id="ddc35-130">Description</span><span class="sxs-lookup"><span data-stu-id="ddc35-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ddc35-131">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ddc35-131">Enumeration</span></span>|<span data-ttu-id="ddc35-132">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="ddc35-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ddc35-133">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="ddc35-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ddc35-134">Valore</span><span class="sxs-lookup"><span data-stu-id="ddc35-134">Value</span></span>|<span data-ttu-id="ddc35-135">Description</span><span class="sxs-lookup"><span data-stu-id="ddc35-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ddc35-136">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ddc35-136">Enumeration</span></span>|<span data-ttu-id="ddc35-137">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ddc35-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ddc35-138">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="ddc35-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="ddc35-139">Valore</span><span class="sxs-lookup"><span data-stu-id="ddc35-139">Value</span></span>|<span data-ttu-id="ddc35-140">Description</span><span class="sxs-lookup"><span data-stu-id="ddc35-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ddc35-141">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ddc35-141">Enumeration</span></span>|<span data-ttu-id="ddc35-142">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="ddc35-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddc35-143">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ddc35-143">Child Elements</span></span>  
 <span data-ttu-id="ddc35-144">No.</span><span class="sxs-lookup"><span data-stu-id="ddc35-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddc35-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ddc35-145">Parent Elements</span></span>  
  
|<span data-ttu-id="ddc35-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddc35-146">Element</span></span>|<span data-ttu-id="ddc35-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddc35-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="ddc35-148">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="ddc35-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddc35-149">Commenti</span><span class="sxs-lookup"><span data-stu-id="ddc35-149">Remarks</span></span>  
 <span data-ttu-id="ddc35-150">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, il certificato specificato mediante questo elemento di configurazione viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="ddc35-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="ddc35-151">Può contenere un solo certificato da usare quando il servizio non specifica alcun certificato.</span><span class="sxs-lookup"><span data-stu-id="ddc35-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddc35-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddc35-152">Example</span></span>  
 <span data-ttu-id="ddc35-153">Nell'esempio seguente viene specificato un certificato da utilizzare per gli endpoint il cui URI inizia con `http://www.contoso.com` e un certificato da utilizzare per tutti gli altri endpoint che non eseguono la negoziazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="ddc35-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddc35-154">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ddc35-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="ddc35-155">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="ddc35-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="ddc35-156">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="ddc35-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ddc35-157">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="ddc35-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
