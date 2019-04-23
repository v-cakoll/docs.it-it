---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 5c20baecf3e9fe83385c986e3fb58f0c03eeeb47
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224195"
---
# <a name="knowncertificates"></a><span data-ttu-id="176f1-101">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="176f1-101">\<knownCertificates></span></span>
<span data-ttu-id="176f1-102">Rappresenta una raccolta di certificati X.509 che vengono forniti per autenticare credenziali di sicurezza pubblicate da un servizio token di sicurezza (STS, Security Token Service).</span><span class="sxs-lookup"><span data-stu-id="176f1-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="176f1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="176f1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="176f1-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="176f1-104">\<behaviors></span></span>  
<span data-ttu-id="176f1-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="176f1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="176f1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="176f1-106">\<behavior></span></span>  
<span data-ttu-id="176f1-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="176f1-107">\<serviceCredentials></span></span>  
<span data-ttu-id="176f1-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="176f1-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="176f1-109">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="176f1-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176f1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="176f1-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="176f1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="176f1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="176f1-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="176f1-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="176f1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="176f1-113">Attributes</span></span>  
 <span data-ttu-id="176f1-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="176f1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="176f1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="176f1-115">Child Elements</span></span>  
  
|<span data-ttu-id="176f1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="176f1-116">Element</span></span>|<span data-ttu-id="176f1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="176f1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="176f1-118">\<add></span><span class="sxs-lookup"><span data-stu-id="176f1-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="176f1-119">Aggiunge un certificato X.509 alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="176f1-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="176f1-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="176f1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="176f1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="176f1-121">Element</span></span>|<span data-ttu-id="176f1-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="176f1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="176f1-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="176f1-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="176f1-124">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="176f1-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="176f1-125">Note</span><span class="sxs-lookup"><span data-stu-id="176f1-125">Remarks</span></span>  
 <span data-ttu-id="176f1-126">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="176f1-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="176f1-127">Nella prima fase, un client tenta di accedere a un servizio viene reindirizzato a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="176f1-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="176f1-128">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="176f1-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="176f1-129">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="176f1-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="176f1-130">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="176f1-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="176f1-131">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="176f1-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="176f1-132">Il [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per tutti questi certificati di servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="176f1-132">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="176f1-133">Per aggiungere i certificati, usare il [ \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="176f1-133">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="176f1-134">Inserire un [ \<Aggiungi >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="176f1-134">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="176f1-135">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="176f1-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="176f1-136">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="176f1-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="176f1-137">Per le condizioni necessarie per un client da autenticare presso un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="176f1-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="176f1-138">Per altre informazioni sugli scenari federati, vedere [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="176f1-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="176f1-139">Per un esempio che illustra come popolare la raccolta nella configurazione, vedere [ \<Aggiungi >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="176f1-139">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176f1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="176f1-140">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="176f1-141">\<add></span><span class="sxs-lookup"><span data-stu-id="176f1-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="176f1-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="176f1-142">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="176f1-143">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="176f1-143">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="176f1-144">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="176f1-144">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="176f1-145">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="176f1-145">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="176f1-146">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="176f1-146">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="176f1-147">\<add></span><span class="sxs-lookup"><span data-stu-id="176f1-147">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="176f1-148">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="176f1-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
