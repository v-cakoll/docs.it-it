---
title: <add>dell' <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398337"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="dd0fb-102">\<add>dell' \<scopedCertificates> elemento</span><span class="sxs-lookup"><span data-stu-id="dd0fb-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="dd0fb-103">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="dd0fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd0fb-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd0fb-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd0fb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="dd0fb-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd0fb-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd0fb-107">Attributes</span></span>  
  
|<span data-ttu-id="dd0fb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd0fb-108">Attribute</span></span>|<span data-ttu-id="dd0fb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd0fb-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="dd0fb-110">targetUri</span></span>|<span data-ttu-id="dd0fb-111">Stringa.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-111">String.</span></span> <span data-ttu-id="dd0fb-112">Specifica l'URI del servizio associato al certificato.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="dd0fb-113">findValue</span><span class="sxs-lookup"><span data-stu-id="dd0fb-113">findValue</span></span>|<span data-ttu-id="dd0fb-114">Stringa.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-114">String.</span></span> <span data-ttu-id="dd0fb-115">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-115">The value to search for.</span></span>|  
|<span data-ttu-id="dd0fb-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="dd0fb-116">x509FindType</span></span>|<span data-ttu-id="dd0fb-117">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-117">Enumeration.</span></span> <span data-ttu-id="dd0fb-118">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="dd0fb-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="dd0fb-119">storeLocation</span></span>|<span data-ttu-id="dd0fb-120">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-120">Enumeration.</span></span> <span data-ttu-id="dd0fb-121">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="dd0fb-122">storeName</span><span class="sxs-lookup"><span data-stu-id="dd0fb-122">storeName</span></span>|<span data-ttu-id="dd0fb-123">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-123">Enumeration.</span></span> <span data-ttu-id="dd0fb-124">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="dd0fb-125">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="dd0fb-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="dd0fb-126">Valore</span><span class="sxs-lookup"><span data-stu-id="dd0fb-126">Value</span></span>|<span data-ttu-id="dd0fb-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd0fb-128">string</span><span class="sxs-lookup"><span data-stu-id="dd0fb-128">String</span></span>|<span data-ttu-id="dd0fb-129">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="dd0fb-130">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="dd0fb-131">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="dd0fb-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="dd0fb-132">Valore</span><span class="sxs-lookup"><span data-stu-id="dd0fb-132">Value</span></span>|<span data-ttu-id="dd0fb-133">Description</span><span class="sxs-lookup"><span data-stu-id="dd0fb-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd0fb-134">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-134">Enumeration</span></span>|<span data-ttu-id="dd0fb-135">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="dd0fb-136">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="dd0fb-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="dd0fb-137">Valore</span><span class="sxs-lookup"><span data-stu-id="dd0fb-137">Value</span></span>|<span data-ttu-id="dd0fb-138">Description</span><span class="sxs-lookup"><span data-stu-id="dd0fb-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd0fb-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-139">Enumeration</span></span>|<span data-ttu-id="dd0fb-140">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="dd0fb-141">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="dd0fb-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="dd0fb-142">Valore</span><span class="sxs-lookup"><span data-stu-id="dd0fb-142">Value</span></span>|<span data-ttu-id="dd0fb-143">Description</span><span class="sxs-lookup"><span data-stu-id="dd0fb-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd0fb-144">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-144">Enumeration</span></span>|<span data-ttu-id="dd0fb-145">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd0fb-146">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd0fb-146">Child Elements</span></span>  
 <span data-ttu-id="dd0fb-147">No.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd0fb-148">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd0fb-148">Parent Elements</span></span>  
  
|<span data-ttu-id="dd0fb-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd0fb-149">Element</span></span>|<span data-ttu-id="dd0fb-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd0fb-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="dd0fb-151">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd0fb-152">Commenti</span><span class="sxs-lookup"><span data-stu-id="dd0fb-152">Remarks</span></span>  
 <span data-ttu-id="dd0fb-153">Questo elemento consente al client di configurare un certificato del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="dd0fb-154">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="dd0fb-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="dd0fb-155">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="dd0fb-156">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="dd0fb-157">Per ulteriori informazioni, vedere la sezione "certificati con ambito" di [procedura: creare un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="dd0fb-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd0fb-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd0fb-158">Example</span></span>  
 <span data-ttu-id="dd0fb-159">Nell'esempio seguente un certificato X.509 viene aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="dd0fb-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd0fb-160">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dd0fb-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="dd0fb-161">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="dd0fb-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="dd0fb-162">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="dd0fb-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="dd0fb-163">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="dd0fb-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="dd0fb-164">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="dd0fb-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
