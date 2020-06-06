---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400327"
---
# \<knownCertificates>
<span data-ttu-id="16243-101">Rappresenta una raccolta di certificati X.509 che vengono forniti per autenticare credenziali di sicurezza pubblicate da un servizio token di sicurezza (STS, Security Token Service).</span><span class="sxs-lookup"><span data-stu-id="16243-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="16243-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16243-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16243-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="16243-103">Attributes and Elements</span></span>  
 <span data-ttu-id="16243-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="16243-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16243-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="16243-105">Attributes</span></span>  
 <span data-ttu-id="16243-106">No.</span><span class="sxs-lookup"><span data-stu-id="16243-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16243-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="16243-107">Child Elements</span></span>  
  
|<span data-ttu-id="16243-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="16243-108">Element</span></span>|<span data-ttu-id="16243-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16243-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="16243-110">Aggiunge un certificato X.509 alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="16243-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16243-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="16243-111">Parent Elements</span></span>  
  
|<span data-ttu-id="16243-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="16243-112">Element</span></span>|<span data-ttu-id="16243-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16243-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="16243-114">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="16243-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16243-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="16243-115">Remarks</span></span>  
 <span data-ttu-id="16243-116">L'emissione di un token di autenticazione prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="16243-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="16243-117">Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*.</span><span class="sxs-lookup"><span data-stu-id="16243-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="16243-118">Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language),</span><span class="sxs-lookup"><span data-stu-id="16243-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="16243-119">che il client restituisce in seguito al servizio.</span><span class="sxs-lookup"><span data-stu-id="16243-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="16243-120">Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client.</span><span class="sxs-lookup"><span data-stu-id="16243-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="16243-121">Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16243-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="16243-122">L' [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per i certificati del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16243-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="16243-123">Per aggiungere certificati, utilizzare l' [ \<knownCertificates> elemento](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="16243-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="16243-124">Inserire un [\<add>](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="16243-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="16243-125">Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16243-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="16243-126">Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="16243-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="16243-127">Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="16243-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="16243-128">Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="16243-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="16243-129">Per un esempio in cui viene illustrato come popolare la raccolta nella configurazione, vedere [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="16243-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16243-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="16243-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="16243-131">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16243-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="16243-132">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="16243-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="16243-133">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="16243-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="16243-134">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="16243-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="16243-135">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="16243-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
