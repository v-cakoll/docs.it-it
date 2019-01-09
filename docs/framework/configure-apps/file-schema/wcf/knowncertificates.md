---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: ed2bd5ec5b3a2a3e7b929b954df1c00be0849d71
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149759"
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="c9178-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="c9178-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="c9178-103">Rappresenta una raccolta di certificati X.509 che vengono forniti per autenticare credenziali di sicurezza pubblicate da un servizio token di sicurezza (STS, Security Token Service).</span><span class="sxs-lookup"><span data-stu-id="c9178-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="c9178-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9178-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9178-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="c9178-105">\<behaviors></span></span>  
<span data-ttu-id="c9178-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c9178-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c9178-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="c9178-107">\<behavior></span></span>  
<span data-ttu-id="c9178-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c9178-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c9178-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="c9178-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="c9178-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="c9178-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9178-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9178-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9178-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c9178-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c9178-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c9178-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9178-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="c9178-114">Attributes</span></span>  
 <span data-ttu-id="c9178-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c9178-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9178-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c9178-116">Child Elements</span></span>  
  
|<span data-ttu-id="c9178-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9178-117">Element</span></span>|<span data-ttu-id="c9178-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9178-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9178-119">\<add></span><span class="sxs-lookup"><span data-stu-id="c9178-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="c9178-120">Aggiunge un certificato X.509 alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="c9178-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9178-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c9178-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c9178-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9178-122">Element</span></span>|<span data-ttu-id="c9178-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9178-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9178-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="c9178-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="c9178-125">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="c9178-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9178-126">Note</span><span class="sxs-lookup"><span data-stu-id="c9178-126">Remarks</span></span>  
 <span data-ttu-id="c9178-127">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="c9178-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="c9178-128">Nella prima fase, un client tenta di accedere a un servizio viene reindirizzato a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="c9178-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="c9178-129">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="c9178-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="c9178-130">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="c9178-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="c9178-131">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="c9178-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="c9178-132">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c9178-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="c9178-133">Il [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per tutti questi certificati di servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c9178-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="c9178-134">Per aggiungere i certificati, usare il [ \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="c9178-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="c9178-135">Inserire un [ \<Aggiungi >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c9178-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="c9178-136">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c9178-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="c9178-137">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="c9178-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="c9178-138">Per le condizioni necessarie per un client da autenticare presso un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="c9178-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="c9178-139">Per altre informazioni sugli scenari federati, vedere [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="c9178-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="c9178-140">Per un esempio che illustra come popolare la raccolta nella configurazione, vedere [ \<Aggiungi >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="c9178-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9178-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9178-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="c9178-142">\<add></span><span class="sxs-lookup"><span data-stu-id="c9178-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="c9178-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="c9178-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="c9178-144">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9178-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="c9178-145">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="c9178-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="c9178-146">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="c9178-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="c9178-147">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c9178-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c9178-148">\<add></span><span class="sxs-lookup"><span data-stu-id="c9178-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="c9178-149">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c9178-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
