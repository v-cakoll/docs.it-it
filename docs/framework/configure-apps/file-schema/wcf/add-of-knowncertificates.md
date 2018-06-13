---
title: '&lt;add&gt; di &lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 0192c14d5ebc0c84859878b35770e03843b2dd50
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752988"
---
# <a name="ltaddgt-of-ltknowncertificatesgt"></a><span data-ttu-id="f85e6-102">&lt;add&gt; di &lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="f85e6-102">&lt;add&gt; of &lt;knownCertificates&gt;</span></span>
<span data-ttu-id="f85e6-103">Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.</span><span class="sxs-lookup"><span data-stu-id="f85e6-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="f85e6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f85e6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f85e6-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f85e6-105">\<behaviors></span></span>  
<span data-ttu-id="f85e6-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f85e6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f85e6-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f85e6-107">\<behavior></span></span>  
<span data-ttu-id="f85e6-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f85e6-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f85e6-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="f85e6-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="f85e6-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="f85e6-110">\<knownCertificates></span></span>  
<span data-ttu-id="f85e6-111">\<add></span><span class="sxs-lookup"><span data-stu-id="f85e6-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85e6-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f85e6-112">Syntax</span></span>  
  
```xml  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f85e6-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f85e6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f85e6-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f85e6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f85e6-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="f85e6-115">Attributes</span></span>  
  
|<span data-ttu-id="f85e6-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="f85e6-116">Attribute</span></span>|<span data-ttu-id="f85e6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f85e6-118">findValue</span><span class="sxs-lookup"><span data-stu-id="f85e6-118">findValue</span></span>|<span data-ttu-id="f85e6-119">Stringa.</span><span class="sxs-lookup"><span data-stu-id="f85e6-119">String.</span></span> <span data-ttu-id="f85e6-120">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="f85e6-120">The value to search for.</span></span>|  
|<span data-ttu-id="f85e6-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f85e6-121">storeLocation</span></span>|<span data-ttu-id="f85e6-122">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f85e6-122">Enumeration.</span></span> <span data-ttu-id="f85e6-123">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="f85e6-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="f85e6-124">storeName</span><span class="sxs-lookup"><span data-stu-id="f85e6-124">storeName</span></span>|<span data-ttu-id="f85e6-125">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f85e6-125">Enumeration.</span></span> <span data-ttu-id="f85e6-126">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="f85e6-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="f85e6-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f85e6-127">x509FindType</span></span>|<span data-ttu-id="f85e6-128">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f85e6-128">Enumeration.</span></span> <span data-ttu-id="f85e6-129">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="f85e6-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="f85e6-130">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="f85e6-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="f85e6-131">Valore</span><span class="sxs-lookup"><span data-stu-id="f85e6-131">Value</span></span>|<span data-ttu-id="f85e6-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f85e6-133">String</span><span class="sxs-lookup"><span data-stu-id="f85e6-133">String</span></span>|<span data-ttu-id="f85e6-134">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="f85e6-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="f85e6-135">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="f85e6-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="f85e6-136">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="f85e6-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="f85e6-137">Valore</span><span class="sxs-lookup"><span data-stu-id="f85e6-137">Value</span></span>|<span data-ttu-id="f85e6-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f85e6-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="f85e6-139">Enumeration</span></span>|<span data-ttu-id="f85e6-140">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="f85e6-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="f85e6-141">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="f85e6-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="f85e6-142">Valore</span><span class="sxs-lookup"><span data-stu-id="f85e6-142">Value</span></span>|<span data-ttu-id="f85e6-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f85e6-144">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="f85e6-144">Enumeration</span></span>|<span data-ttu-id="f85e6-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f85e6-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="f85e6-146">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="f85e6-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="f85e6-147">Valore</span><span class="sxs-lookup"><span data-stu-id="f85e6-147">Value</span></span>|<span data-ttu-id="f85e6-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f85e6-149">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="f85e6-149">Enumeration</span></span>|<span data-ttu-id="f85e6-150">I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="f85e6-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f85e6-151">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f85e6-151">Child Elements</span></span>  
 <span data-ttu-id="f85e6-152">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f85e6-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f85e6-153">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f85e6-153">Parent Elements</span></span>  
  
|<span data-ttu-id="f85e6-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="f85e6-154">Element</span></span>|<span data-ttu-id="f85e6-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85e6-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f85e6-156">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="f85e6-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="f85e6-157">Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f85e6-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f85e6-158">Note</span><span class="sxs-lookup"><span data-stu-id="f85e6-158">Remarks</span></span>  
 <span data-ttu-id="f85e6-159">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="f85e6-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="f85e6-160">Nella prima fase, un client sta tentando di accedere a un servizio viene reindirizzato a un *secure token service*.</span><span class="sxs-lookup"><span data-stu-id="f85e6-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="f85e6-161">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="f85e6-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="f85e6-162">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="f85e6-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="f85e6-163">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="f85e6-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="f85e6-164">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f85e6-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="f85e6-165">Il [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per i certificati di tale servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f85e6-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="f85e6-166">Per aggiungere i certificati, usare il [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="f85e6-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="f85e6-167">Inserire un [ \<aggiungere > elemento \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f85e6-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="f85e6-168">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f85e6-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="f85e6-169">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="f85e6-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="f85e6-170">Per le condizioni necessarie per un client da autenticare presso un servizio federato, nonché ulteriori informazioni sull'utilizzo di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="f85e6-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="f85e6-171">Per ulteriori informazioni sugli scenari federati, vedere [federazione e i token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="f85e6-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f85e6-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="f85e6-172">Example</span></span>  
 <span data-ttu-id="f85e6-173">Nell'esempio seguente viene aggiunto il certificato al repository per i certificati STS.</span><span class="sxs-lookup"><span data-stu-id="f85e6-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f85e6-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85e6-174">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="f85e6-175">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="f85e6-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)  
 [<span data-ttu-id="f85e6-176">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="f85e6-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="f85e6-177">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="f85e6-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f85e6-178">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="f85e6-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="f85e6-179">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f85e6-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
