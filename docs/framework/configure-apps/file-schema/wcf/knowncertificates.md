---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400327"
---
# <a name="knowncertificates"></a><span data-ttu-id="e11a5-101">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="e11a5-101">\<knownCertificates></span></span>
<span data-ttu-id="e11a5-102">Rappresenta una raccolta di certificati X.509 che vengono forniti per autenticare credenziali di sicurezza pubblicate da un servizio token di sicurezza (STS, Security Token Service).</span><span class="sxs-lookup"><span data-stu-id="e11a5-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="e11a5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e11a5-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e11a5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e11a5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e11a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e11a5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="e11a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenAuthentication**](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="e11a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> knownCertificates**</span><span class="sxs-lookup"><span data-stu-id="e11a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e11a5-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e11a5-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e11a5-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e11a5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e11a5-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e11a5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e11a5-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e11a5-114">Attributes</span></span>  
 <span data-ttu-id="e11a5-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e11a5-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e11a5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e11a5-116">Child Elements</span></span>  
  
|<span data-ttu-id="e11a5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e11a5-117">Element</span></span>|<span data-ttu-id="e11a5-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e11a5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e11a5-119">\<add></span><span class="sxs-lookup"><span data-stu-id="e11a5-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="e11a5-120">Aggiunge un certificato X.509 alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="e11a5-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e11a5-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e11a5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e11a5-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e11a5-122">Element</span></span>|<span data-ttu-id="e11a5-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e11a5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e11a5-124">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e11a5-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e11a5-125">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="e11a5-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e11a5-126">Note</span><span class="sxs-lookup"><span data-stu-id="e11a5-126">Remarks</span></span>  
 <span data-ttu-id="e11a5-127">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="e11a5-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="e11a5-128">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="e11a5-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="e11a5-129">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="e11a5-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="e11a5-130">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="e11a5-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="e11a5-131">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="e11a5-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="e11a5-132">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e11a5-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="e11a5-133">L'elemento > IssuedTokenAuthentication è il repository per i certificati del servizio token di sicurezza di questo tipo. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e11a5-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="e11a5-134">Per aggiungere certificati, usare l' [ \<elemento KnownCertificates >](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="e11a5-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="e11a5-135">Inserire un [ \<> Aggiungi](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e11a5-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="e11a5-136">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e11a5-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="e11a5-137">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="e11a5-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="e11a5-138">Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: Configurare le credenziali in un](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="e11a5-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="e11a5-139">Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="e11a5-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="e11a5-140">Per un esempio in cui viene illustrato come popolare la raccolta nella configurazione, vedere [ \<aggiungere >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="e11a5-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e11a5-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e11a5-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="e11a5-142">\<add></span><span class="sxs-lookup"><span data-stu-id="e11a5-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="e11a5-143">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e11a5-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="e11a5-144">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e11a5-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e11a5-145">Procedura: Configurare le credenziali in un Servizio federativo</span><span class="sxs-lookup"><span data-stu-id="e11a5-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="e11a5-146">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="e11a5-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e11a5-147">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="e11a5-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e11a5-148">\<add></span><span class="sxs-lookup"><span data-stu-id="e11a5-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="e11a5-149">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e11a5-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
