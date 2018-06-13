---
title: '&lt;issuedTokenAuthentication&gt; di &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 87e96e5942a02069371462b8c6301e03f681d5ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749969"
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="dfa93-102">&lt;issuedTokenAuthentication&gt; di &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="dfa93-102">&lt;issuedTokenAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="dfa93-103">Specifica un token personalizzato emesso come credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa93-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="dfa93-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dfa93-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dfa93-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="dfa93-105">\<behaviors></span></span>  
<span data-ttu-id="dfa93-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dfa93-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dfa93-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="dfa93-107">\<behavior></span></span>  
<span data-ttu-id="dfa93-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="dfa93-108">\<serviceCredentials></span></span>  
<span data-ttu-id="dfa93-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="dfa93-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfa93-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfa93-110">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication   
   allowUntrustedRsaIssuers="Boolean"  
   audienceUriMode="Always/BearerKeyOnly/Never"  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   samlSerializer="String"  
    trustedStoreLocation="CurrentUser/LocalMachine">  
      <allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
      </allowedAudienceUris>  
      <knownCertificates>   
         <add findValue="String"  
                 storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
      </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfa93-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dfa93-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dfa93-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dfa93-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfa93-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="dfa93-113">Attributes</span></span>  
  
|<span data-ttu-id="dfa93-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="dfa93-114">Attribute</span></span>|<span data-ttu-id="dfa93-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfa93-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="dfa93-116">Ottiene il set di URI di destinazione a cui il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché sia considerato valido dall'istanza di un oggetto <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="dfa93-117">Per altre informazioni sull'utilizzo di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="dfa93-118">Valore booleano che specifica se sono consentiti emittenti di certificati RSA non attendibili.</span><span class="sxs-lookup"><span data-stu-id="dfa93-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="dfa93-119">I certificati sono firmati dalle Autorità di certificazione (CA) per verificarne l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="dfa93-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="dfa93-120">Un emittente non attendibile è un'autorità di certificazione che non è specificata come attendibile per la firma di certificati.</span><span class="sxs-lookup"><span data-stu-id="dfa93-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="dfa93-121">Ottiene un valore che specifica se occorre convalidare la condizione <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token di sicurezza <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="dfa93-122">Questo valore è di tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="dfa93-123">Per altre informazioni sull'utilizzo di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="dfa93-124">Imposta la modalità di convalida dei certificati.</span><span class="sxs-lookup"><span data-stu-id="dfa93-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="dfa93-125">Uno dei valori validi di <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="dfa93-126">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="dfa93-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="dfa93-127">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="dfa93-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="dfa93-128">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="dfa93-128">Optional string.</span></span> <span data-ttu-id="dfa93-129">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="dfa93-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="dfa93-130">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="dfa93-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="dfa93-131">Imposta la modalità di revoca che specifica se viene eseguito un controllo di revoca e se viene eseguito in linea o non in linea.</span><span class="sxs-lookup"><span data-stu-id="dfa93-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="dfa93-132">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="dfa93-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="dfa93-133">Attributo stringa facoltativo che specifica il tipo di serializzatore SamlSerializer usato per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa93-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="dfa93-134">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="dfa93-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="dfa93-135">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="dfa93-135">Optional enumeration.</span></span> <span data-ttu-id="dfa93-136">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="dfa93-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfa93-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dfa93-137">Child Elements</span></span>  
  
|<span data-ttu-id="dfa93-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfa93-138">Element</span></span>|<span data-ttu-id="dfa93-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfa93-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="dfa93-140">Specifica una raccolta di elementi <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> che specificano emittenti attendibili per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa93-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfa93-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dfa93-141">Parent Elements</span></span>  
  
|<span data-ttu-id="dfa93-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfa93-142">Element</span></span>|<span data-ttu-id="dfa93-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfa93-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfa93-144">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="dfa93-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="dfa93-145">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="dfa93-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfa93-146">Note</span><span class="sxs-lookup"><span data-stu-id="dfa93-146">Remarks</span></span>  
 <span data-ttu-id="dfa93-147">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="dfa93-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="dfa93-148">Nella prima fase, un client sta tentando di accedere a un servizio viene reindirizzato a un *secure token service*.</span><span class="sxs-lookup"><span data-stu-id="dfa93-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="dfa93-149">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="dfa93-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="dfa93-150">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa93-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="dfa93-151">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="dfa93-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="dfa93-152">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dfa93-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="dfa93-153">Questo elemento rappresenta il repository dei certificati usati dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dfa93-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="dfa93-154">Per aggiungere i certificati, usare il [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="dfa93-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="dfa93-155">Inserire un [ \<aggiungere >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthorization>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="dfa93-156">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dfa93-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="dfa93-157">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa93-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="dfa93-158">Per ulteriori informazioni sull'utilizzo di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="dfa93-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa93-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfa93-159">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
 [<span data-ttu-id="dfa93-160">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="dfa93-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="dfa93-161">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="dfa93-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
