---
title: <add> di <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400615"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="7ace4-102">\<add> di \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="7ace4-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="7ace4-103">Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.</span><span class="sxs-lookup"><span data-stu-id="7ace4-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7ace4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ace4-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ace4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7ace4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7ace4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7ace4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ace4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7ace4-107">Attributes</span></span>  
  
|<span data-ttu-id="7ace4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7ace4-108">Attribute</span></span>|<span data-ttu-id="7ace4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ace4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ace4-110">findValue</span><span class="sxs-lookup"><span data-stu-id="7ace4-110">findValue</span></span>|<span data-ttu-id="7ace4-111">Stringa.</span><span class="sxs-lookup"><span data-stu-id="7ace4-111">String.</span></span> <span data-ttu-id="7ace4-112">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="7ace4-112">The value to search for.</span></span>|  
|<span data-ttu-id="7ace4-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="7ace4-113">storeLocation</span></span>|<span data-ttu-id="7ace4-114">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7ace4-114">Enumeration.</span></span> <span data-ttu-id="7ace4-115">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="7ace4-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="7ace4-116">storeName</span><span class="sxs-lookup"><span data-stu-id="7ace4-116">storeName</span></span>|<span data-ttu-id="7ace4-117">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7ace4-117">Enumeration.</span></span> <span data-ttu-id="7ace4-118">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="7ace4-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="7ace4-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="7ace4-119">x509FindType</span></span>|<span data-ttu-id="7ace4-120">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7ace4-120">Enumeration.</span></span> <span data-ttu-id="7ace4-121">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="7ace4-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="7ace4-122">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="7ace4-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="7ace4-123">Valore</span><span class="sxs-lookup"><span data-stu-id="7ace4-123">Value</span></span>|<span data-ttu-id="7ace4-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ace4-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ace4-125">string</span><span class="sxs-lookup"><span data-stu-id="7ace4-125">String</span></span>|<span data-ttu-id="7ace4-126">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="7ace4-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="7ace4-127">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="7ace4-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="7ace4-128">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="7ace4-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="7ace4-129">Valore</span><span class="sxs-lookup"><span data-stu-id="7ace4-129">Value</span></span>|<span data-ttu-id="7ace4-130">Description</span><span class="sxs-lookup"><span data-stu-id="7ace4-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ace4-131">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="7ace4-131">Enumeration</span></span>|<span data-ttu-id="7ace4-132">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="7ace4-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="7ace4-133">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="7ace4-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="7ace4-134">Valore</span><span class="sxs-lookup"><span data-stu-id="7ace4-134">Value</span></span>|<span data-ttu-id="7ace4-135">Description</span><span class="sxs-lookup"><span data-stu-id="7ace4-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ace4-136">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="7ace4-136">Enumeration</span></span>|<span data-ttu-id="7ace4-137">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="7ace4-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="7ace4-138">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="7ace4-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="7ace4-139">Valore</span><span class="sxs-lookup"><span data-stu-id="7ace4-139">Value</span></span>|<span data-ttu-id="7ace4-140">Description</span><span class="sxs-lookup"><span data-stu-id="7ace4-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ace4-141">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="7ace4-141">Enumeration</span></span>|<span data-ttu-id="7ace4-142">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="7ace4-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ace4-143">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7ace4-143">Child Elements</span></span>  
 <span data-ttu-id="7ace4-144">No.</span><span class="sxs-lookup"><span data-stu-id="7ace4-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ace4-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7ace4-145">Parent Elements</span></span>  
  
|<span data-ttu-id="7ace4-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ace4-146">Element</span></span>|<span data-ttu-id="7ace4-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ace4-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="7ace4-148">Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7ace4-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ace4-149">Commenti</span><span class="sxs-lookup"><span data-stu-id="7ace4-149">Remarks</span></span>  
 <span data-ttu-id="7ace4-150">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="7ace4-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="7ace4-151">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="7ace4-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="7ace4-152">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="7ace4-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="7ace4-153">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="7ace4-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="7ace4-154">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="7ace4-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="7ace4-155">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7ace4-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="7ace4-156">L' [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per i certificati del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7ace4-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="7ace4-157">Per aggiungere certificati, utilizzare [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="7ace4-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="7ace4-158">Inserire un [ \<add> \<knownCertificates> elemento element](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7ace4-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="7ace4-159">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7ace4-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="7ace4-160">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="7ace4-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="7ace4-161">Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="7ace4-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="7ace4-162">Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="7ace4-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ace4-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ace4-163">Example</span></span>  
 <span data-ttu-id="7ace4-164">Nell'esempio seguente viene aggiunto il certificato al repository per i certificati STS.</span><span class="sxs-lookup"><span data-stu-id="7ace4-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="7ace4-165">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7ace4-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="7ace4-166">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="7ace4-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7ace4-167">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="7ace4-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7ace4-168">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="7ace4-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="7ace4-169">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="7ace4-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
