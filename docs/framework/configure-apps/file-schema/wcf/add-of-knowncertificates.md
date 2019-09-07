---
title: <add> di <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400615"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="429cf-102">\<aggiungere > di \<KnownCertificates ></span><span class="sxs-lookup"><span data-stu-id="429cf-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="429cf-103">Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.</span><span class="sxs-lookup"><span data-stu-id="429cf-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="429cf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="429cf-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="429cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="429cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="429cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="429cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="429cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenAuthentication**](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="429cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> knownCertificates**](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="429cf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="429cf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="429cf-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="429cf-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="429cf-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="429cf-114">Attributes and Elements</span></span>  
 <span data-ttu-id="429cf-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="429cf-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="429cf-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="429cf-116">Attributes</span></span>  
  
|<span data-ttu-id="429cf-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="429cf-117">Attribute</span></span>|<span data-ttu-id="429cf-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="429cf-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="429cf-119">findValue</span><span class="sxs-lookup"><span data-stu-id="429cf-119">findValue</span></span>|<span data-ttu-id="429cf-120">Stringa.</span><span class="sxs-lookup"><span data-stu-id="429cf-120">String.</span></span> <span data-ttu-id="429cf-121">Valore da cercare.</span><span class="sxs-lookup"><span data-stu-id="429cf-121">The value to search for.</span></span>|  
|<span data-ttu-id="429cf-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="429cf-122">storeLocation</span></span>|<span data-ttu-id="429cf-123">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="429cf-123">Enumeration.</span></span> <span data-ttu-id="429cf-124">Uno di due percorsi dell'archivio in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="429cf-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="429cf-125">storeName</span><span class="sxs-lookup"><span data-stu-id="429cf-125">storeName</span></span>|<span data-ttu-id="429cf-126">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="429cf-126">Enumeration.</span></span> <span data-ttu-id="429cf-127">Uno degli archivi di sistema in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="429cf-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="429cf-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="429cf-128">x509FindType</span></span>|<span data-ttu-id="429cf-129">Enumerazione.</span><span class="sxs-lookup"><span data-stu-id="429cf-129">Enumeration.</span></span> <span data-ttu-id="429cf-130">Uno dei campi certificato in cui cercare.</span><span class="sxs-lookup"><span data-stu-id="429cf-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="429cf-131">Attributo findValue</span><span class="sxs-lookup"><span data-stu-id="429cf-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="429cf-132">Value</span><span class="sxs-lookup"><span data-stu-id="429cf-132">Value</span></span>|<span data-ttu-id="429cf-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="429cf-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="429cf-134">String</span><span class="sxs-lookup"><span data-stu-id="429cf-134">String</span></span>|<span data-ttu-id="429cf-135">Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType.</span><span class="sxs-lookup"><span data-stu-id="429cf-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="429cf-136">Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="429cf-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="429cf-137">Attributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="429cf-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="429cf-138">Value</span><span class="sxs-lookup"><span data-stu-id="429cf-138">Value</span></span>|<span data-ttu-id="429cf-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="429cf-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="429cf-140">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="429cf-140">Enumeration</span></span>|<span data-ttu-id="429cf-141">I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="429cf-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="429cf-142">Attributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="429cf-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="429cf-143">Value</span><span class="sxs-lookup"><span data-stu-id="429cf-143">Value</span></span>|<span data-ttu-id="429cf-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="429cf-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="429cf-145">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="429cf-145">Enumeration</span></span>|<span data-ttu-id="429cf-146">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="429cf-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="429cf-147">Attributo storeName</span><span class="sxs-lookup"><span data-stu-id="429cf-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="429cf-148">Value</span><span class="sxs-lookup"><span data-stu-id="429cf-148">Value</span></span>|<span data-ttu-id="429cf-149">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="429cf-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="429cf-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="429cf-150">Enumeration</span></span>|<span data-ttu-id="429cf-151">I valori includono: AddressBook, AuthRoot, CertificateAuthority, non consentito, My, root, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="429cf-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="429cf-152">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="429cf-152">Child Elements</span></span>  
 <span data-ttu-id="429cf-153">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="429cf-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="429cf-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="429cf-154">Parent Elements</span></span>  
  
|<span data-ttu-id="429cf-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="429cf-155">Element</span></span>|<span data-ttu-id="429cf-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="429cf-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="429cf-157">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="429cf-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="429cf-158">Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="429cf-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="429cf-159">Note</span><span class="sxs-lookup"><span data-stu-id="429cf-159">Remarks</span></span>  
 <span data-ttu-id="429cf-160">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="429cf-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="429cf-161">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="429cf-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="429cf-162">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="429cf-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="429cf-163">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="429cf-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="429cf-164">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="429cf-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="429cf-165">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="429cf-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="429cf-166">L'elemento > IssuedTokenAuthentication è il repository per i certificati del servizio token di sicurezza di questo tipo. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="429cf-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="429cf-167">Per aggiungere certificati, usare il [ \<> KnownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="429cf-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="429cf-168">Inserire un [ \<elemento Add > \<element KnownCertificates >](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="429cf-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="429cf-169">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="429cf-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="429cf-170">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="429cf-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="429cf-171">Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: Configurare le credenziali in un](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="429cf-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="429cf-172">Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="429cf-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="429cf-173">Esempio</span><span class="sxs-lookup"><span data-stu-id="429cf-173">Example</span></span>  
 <span data-ttu-id="429cf-174">Nell'esempio seguente viene aggiunto il certificato al repository per i certificati STS.</span><span class="sxs-lookup"><span data-stu-id="429cf-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="429cf-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="429cf-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="429cf-176">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="429cf-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="429cf-177">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="429cf-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="429cf-178">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="429cf-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="429cf-179">Procedura: Configurare le credenziali in un Servizio federativo</span><span class="sxs-lookup"><span data-stu-id="429cf-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="429cf-180">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="429cf-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
