---
title: <add> di <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 939718e8dacca2698b6f71a3bdc1262a5dc3ee20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926685"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="60ed9-102">\<aggiungere > di \<KnownCertificates ></span><span class="sxs-lookup"><span data-stu-id="60ed9-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="60ed9-103">Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.</span><span class="sxs-lookup"><span data-stu-id="60ed9-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="60ed9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60ed9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="60ed9-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="60ed9-105">\<behaviors></span></span>  
<span data-ttu-id="60ed9-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="60ed9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="60ed9-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="60ed9-107">\<behavior></span></span>  
<span data-ttu-id="60ed9-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="60ed9-108">\<serviceCredentials></span></span>  
<span data-ttu-id="60ed9-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="60ed9-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="60ed9-110">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="60ed9-110">\<knownCertificates></span></span>  
<span data-ttu-id="60ed9-111">\<add></span><span class="sxs-lookup"><span data-stu-id="60ed9-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ed9-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60ed9-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60ed9-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="60ed9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="60ed9-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="60ed9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60ed9-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="60ed9-115">Attributes</span></span>  
  
|<span data-ttu-id="60ed9-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="60ed9-116">Attribute</span></span>|<span data-ttu-id="60ed9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ed9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60ed9-118">findValue</span><span class="sxs-lookup"><span data-stu-id="60ed9-118">findValue</span></span>|<span data-ttu-id="60ed9-119">Stringa.</span><span class="sxs-lookup"><span data-stu-id="60ed9-119">String.</span></span> <span data-ttu-id="60ed9-120">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="60ed9-120">The value to search for.</span></span>|  
|<span data-ttu-id="60ed9-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="60ed9-121">storeLocation</span></span>|<span data-ttu-id="60ed9-122">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="60ed9-122">Enumeration.</span></span> <span data-ttu-id="60ed9-123">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="60ed9-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="60ed9-124">storeName</span><span class="sxs-lookup"><span data-stu-id="60ed9-124">storeName</span></span>|<span data-ttu-id="60ed9-125">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="60ed9-125">Enumeration.</span></span> <span data-ttu-id="60ed9-126">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="60ed9-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="60ed9-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="60ed9-127">x509FindType</span></span>|<span data-ttu-id="60ed9-128">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="60ed9-128">Enumeration.</span></span> <span data-ttu-id="60ed9-129">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="60ed9-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="60ed9-130">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="60ed9-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="60ed9-131">Value</span><span class="sxs-lookup"><span data-stu-id="60ed9-131">Value</span></span>|<span data-ttu-id="60ed9-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ed9-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60ed9-133">String</span><span class="sxs-lookup"><span data-stu-id="60ed9-133">String</span></span>|<span data-ttu-id="60ed9-134">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="60ed9-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="60ed9-135">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="60ed9-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="60ed9-136">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="60ed9-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="60ed9-137">Valore</span><span class="sxs-lookup"><span data-stu-id="60ed9-137">Value</span></span>|<span data-ttu-id="60ed9-138">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="60ed9-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60ed9-139">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="60ed9-139">Enumeration</span></span>|<span data-ttu-id="60ed9-140">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="60ed9-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="60ed9-141">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="60ed9-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="60ed9-142">Valore</span><span class="sxs-lookup"><span data-stu-id="60ed9-142">Value</span></span>|<span data-ttu-id="60ed9-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ed9-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60ed9-144">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="60ed9-144">Enumeration</span></span>|<span data-ttu-id="60ed9-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="60ed9-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="60ed9-146">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="60ed9-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="60ed9-147">Valore</span><span class="sxs-lookup"><span data-stu-id="60ed9-147">Value</span></span>|<span data-ttu-id="60ed9-148">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="60ed9-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60ed9-149">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="60ed9-149">Enumeration</span></span>|<span data-ttu-id="60ed9-150">I valori includono: AddressBook, AuthRoot, CertificateAuthority, non consentito, My, root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="60ed9-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60ed9-151">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="60ed9-151">Child Elements</span></span>  
 <span data-ttu-id="60ed9-152">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="60ed9-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60ed9-153">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="60ed9-153">Parent Elements</span></span>  
  
|<span data-ttu-id="60ed9-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="60ed9-154">Element</span></span>|<span data-ttu-id="60ed9-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ed9-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60ed9-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="60ed9-156">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="60ed9-157">Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="60ed9-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ed9-158">Note</span><span class="sxs-lookup"><span data-stu-id="60ed9-158">Remarks</span></span>  
 <span data-ttu-id="60ed9-159">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="60ed9-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="60ed9-160">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="60ed9-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="60ed9-161">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="60ed9-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="60ed9-162">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="60ed9-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="60ed9-163">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="60ed9-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="60ed9-164">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="60ed9-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="60ed9-165">L'elemento > IssuedTokenAuthentication è il repository per i certificati del servizio token di sicurezza di questo tipo. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="60ed9-165">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="60ed9-166">Per aggiungere certificati, usare il [ \<> KnownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="60ed9-166">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="60ed9-167">Inserire un [ \<elemento Add > \<element KnownCertificates >](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="60ed9-167">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="60ed9-168">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="60ed9-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="60ed9-169">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="60ed9-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="60ed9-170">Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: Configurare le credenziali in un](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="60ed9-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="60ed9-171">Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="60ed9-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60ed9-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="60ed9-172">Example</span></span>  
 <span data-ttu-id="60ed9-173">Nell'esempio seguente viene aggiunto il certificato al repository per i certificati STS.</span><span class="sxs-lookup"><span data-stu-id="60ed9-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60ed9-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60ed9-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="60ed9-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="60ed9-175">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="60ed9-176">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="60ed9-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="60ed9-177">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="60ed9-177">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="60ed9-178">Procedura: Configurare le credenziali in un Servizio federativo</span><span class="sxs-lookup"><span data-stu-id="60ed9-178">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="60ed9-179">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="60ed9-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
