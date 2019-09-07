---
title: <issuedTokenAuthentication> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400364"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="97a0d-102">\<IssuedTokenAuthentication > di \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="97a0d-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="97a0d-103">Specifica un token personalizzato emesso come credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="97a0d-103">Specifies a custom token issued as a service credential.</span></span>  
  
<span data-ttu-id="97a0d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97a0d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="97a0d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="97a0d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="97a0d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="97a0d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="97a0d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="97a0d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuedTokenAuthentication**</span><span class="sxs-lookup"><span data-stu-id="97a0d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a0d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97a0d-111">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97a0d-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97a0d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97a0d-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97a0d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97a0d-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="97a0d-114">Attributes</span></span>  
  
|<span data-ttu-id="97a0d-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="97a0d-115">Attribute</span></span>|<span data-ttu-id="97a0d-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="97a0d-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="97a0d-117">Ottiene il set di URI di destinazione a cui il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché sia considerato valido dall'istanza di un oggetto <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-117">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="97a0d-118">Per altre informazioni sull'uso di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-118">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="97a0d-119">Valore booleano che specifica se sono consentiti emittenti di certificati RSA non attendibili.</span><span class="sxs-lookup"><span data-stu-id="97a0d-119">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="97a0d-120">I certificati sono firmati dalle Autorità di certificazione (CA) per verificarne l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="97a0d-120">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="97a0d-121">Un emittente non attendibile è un'autorità di certificazione che non è specificata come attendibile per la firma di certificati.</span><span class="sxs-lookup"><span data-stu-id="97a0d-121">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="97a0d-122">Ottiene un valore che specifica se occorre convalidare la condizione <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token di sicurezza <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-122">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="97a0d-123">Questo valore è di tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-123">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="97a0d-124">Per altre informazioni sull'uso di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-124">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="97a0d-125">Imposta la modalità di convalida dei certificati.</span><span class="sxs-lookup"><span data-stu-id="97a0d-125">Sets the certificate validation mode.</span></span> <span data-ttu-id="97a0d-126">Uno dei valori validi di <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-126">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="97a0d-127">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="97a0d-127">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="97a0d-128">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="97a0d-128">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="97a0d-129">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="97a0d-129">Optional string.</span></span> <span data-ttu-id="97a0d-130">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="97a0d-130">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="97a0d-131">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="97a0d-131">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="97a0d-132">Imposta la modalità di revoca che specifica se viene eseguito un controllo di revoca e se viene eseguito in linea o non in linea.</span><span class="sxs-lookup"><span data-stu-id="97a0d-132">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="97a0d-133">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="97a0d-133">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="97a0d-134">Attributo stringa facoltativo che specifica il tipo di serializzatore SamlSerializer usato per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="97a0d-134">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="97a0d-135">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="97a0d-135">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="97a0d-136">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="97a0d-136">Optional enumeration.</span></span> <span data-ttu-id="97a0d-137">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="97a0d-137">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97a0d-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97a0d-138">Child Elements</span></span>  
  
|<span data-ttu-id="97a0d-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="97a0d-139">Element</span></span>|<span data-ttu-id="97a0d-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97a0d-140">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="97a0d-141">Specifica una raccolta di elementi <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> che specificano emittenti attendibili per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="97a0d-141">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97a0d-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97a0d-142">Parent Elements</span></span>  
  
|<span data-ttu-id="97a0d-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="97a0d-143">Element</span></span>|<span data-ttu-id="97a0d-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97a0d-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97a0d-145">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="97a0d-145">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="97a0d-146">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="97a0d-146">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a0d-147">Note</span><span class="sxs-lookup"><span data-stu-id="97a0d-147">Remarks</span></span>  
 <span data-ttu-id="97a0d-148">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="97a0d-148">The issued token scenario has three stages.</span></span> <span data-ttu-id="97a0d-149">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="97a0d-149">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="97a0d-150">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="97a0d-150">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="97a0d-151">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="97a0d-151">The client then returns to the service with the token.</span></span> <span data-ttu-id="97a0d-152">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="97a0d-152">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="97a0d-153">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="97a0d-153">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="97a0d-154">Questo elemento rappresenta il repository dei certificati usati dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="97a0d-154">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="97a0d-155">Per aggiungere certificati, usare il [ \<> KnownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="97a0d-155">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="97a0d-156">Inserire un [ \<> Aggiungi](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="97a0d-156">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="97a0d-157">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="97a0d-157">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="97a0d-158">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="97a0d-158">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="97a0d-159">Per altre informazioni sull'uso di questo elemento di configurazione [, vedere Procedura: Configurare le credenziali in un](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="97a0d-159">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a0d-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a0d-160">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="97a0d-161">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="97a0d-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="97a0d-162">Procedura: Configurare le credenziali in un Servizio federativo</span><span class="sxs-lookup"><span data-stu-id="97a0d-162">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
