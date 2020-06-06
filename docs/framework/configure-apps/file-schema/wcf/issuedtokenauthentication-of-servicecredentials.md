---
title: <issuedTokenAuthentication> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400364"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="048bb-102">\<issuedTokenAuthentication> di \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="048bb-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="048bb-103">Specifica un token personalizzato emesso come credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="048bb-103">Specifies a custom token issued as a service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="048bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="048bb-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="048bb-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="048bb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="048bb-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="048bb-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="048bb-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="048bb-107">Attributes</span></span>  
  
|<span data-ttu-id="048bb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="048bb-108">Attribute</span></span>|<span data-ttu-id="048bb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="048bb-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="048bb-110">Ottiene il set di URI di destinazione a cui il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché sia considerato valido dall'istanza di un oggetto <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="048bb-110">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="048bb-111">Per altre informazioni sull'uso di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="048bb-111">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="048bb-112">Valore booleano che specifica se sono consentiti emittenti di certificati RSA non attendibili.</span><span class="sxs-lookup"><span data-stu-id="048bb-112">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="048bb-113">I certificati sono firmati dalle Autorità di certificazione (CA) per verificarne l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="048bb-113">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="048bb-114">Un emittente non attendibile è un'autorità di certificazione che non è specificata come attendibile per la firma di certificati.</span><span class="sxs-lookup"><span data-stu-id="048bb-114">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="048bb-115">Ottiene un valore che specifica se occorre convalidare la condizione <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token di sicurezza <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="048bb-115">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="048bb-116">Questo valore è di tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="048bb-116">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="048bb-117">Per altre informazioni sull'uso di questo attributo, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="048bb-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="048bb-118">Imposta la modalità di convalida dei certificati.</span><span class="sxs-lookup"><span data-stu-id="048bb-118">Sets the certificate validation mode.</span></span> <span data-ttu-id="048bb-119">Uno dei valori validi di <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="048bb-119">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="048bb-120">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="048bb-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="048bb-121">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="048bb-121">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="048bb-122">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="048bb-122">Optional string.</span></span> <span data-ttu-id="048bb-123">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="048bb-123">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="048bb-124">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="048bb-124">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="048bb-125">Imposta la modalità di revoca che specifica se viene eseguito un controllo di revoca e se viene eseguito in linea o non in linea.</span><span class="sxs-lookup"><span data-stu-id="048bb-125">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="048bb-126">L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="048bb-126">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="048bb-127">Attributo stringa facoltativo che specifica il tipo di serializzatore SamlSerializer usato per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="048bb-127">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="048bb-128">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="048bb-128">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="048bb-129">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="048bb-129">Optional enumeration.</span></span> <span data-ttu-id="048bb-130">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="048bb-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="048bb-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="048bb-131">Child Elements</span></span>  
  
|<span data-ttu-id="048bb-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="048bb-132">Element</span></span>|<span data-ttu-id="048bb-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="048bb-133">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="048bb-134">Specifica una raccolta di elementi <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> che specificano emittenti attendibili per la credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="048bb-134">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="048bb-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="048bb-135">Parent Elements</span></span>  
  
|<span data-ttu-id="048bb-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="048bb-136">Element</span></span>|<span data-ttu-id="048bb-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="048bb-137">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="048bb-138">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="048bb-138">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="048bb-139">Commenti</span><span class="sxs-lookup"><span data-stu-id="048bb-139">Remarks</span></span>  
 <span data-ttu-id="048bb-140">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="048bb-140">The issued token scenario has three stages.</span></span> <span data-ttu-id="048bb-141">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="048bb-141">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="048bb-142">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="048bb-142">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="048bb-143">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="048bb-143">The client then returns to the service with the token.</span></span> <span data-ttu-id="048bb-144">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="048bb-144">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="048bb-145">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="048bb-145">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="048bb-146">Questo elemento rappresenta il repository dei certificati usati dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="048bb-146">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="048bb-147">Per aggiungere certificati, utilizzare [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="048bb-147">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="048bb-148">Inserire un [\<add>](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="048bb-148">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="048bb-149">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="048bb-149">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="048bb-150">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="048bb-150">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="048bb-151">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="048bb-151">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="048bb-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="048bb-152">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="048bb-153">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="048bb-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="048bb-154">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="048bb-154">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
