---
title: '&lt;allowedAudienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: cbbe817cb647589bf30dfeb6068c2c37536277fe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151851"
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="ce712-102">&lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="ce712-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="ce712-103">Rappresenta una raccolta di URI di destinazione ai quali può essere destinato il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="ce712-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="ce712-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ce712-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ce712-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ce712-105">\<behaviors></span></span>  
<span data-ttu-id="ce712-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ce712-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ce712-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ce712-107">\<behavior></span></span>  
<span data-ttu-id="ce712-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ce712-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ce712-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ce712-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="ce712-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="ce712-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce712-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce712-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce712-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce712-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ce712-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce712-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce712-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce712-114">Attributes</span></span>  
 <span data-ttu-id="ce712-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ce712-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce712-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce712-116">Child Elements</span></span>  
  
|<span data-ttu-id="ce712-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce712-117">Element</span></span>|<span data-ttu-id="ce712-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce712-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce712-119">\<add></span><span class="sxs-lookup"><span data-stu-id="ce712-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="ce712-120">Aggiunge un URI di destinazione al quale il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="ce712-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce712-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce712-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ce712-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce712-122">Element</span></span>|<span data-ttu-id="ce712-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce712-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce712-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ce712-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="ce712-125">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="ce712-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce712-126">Note</span><span class="sxs-lookup"><span data-stu-id="ce712-126">Remarks</span></span>  
 <span data-ttu-id="ce712-127">Usare questa raccolta in un'applicazione federata che usa un servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="ce712-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="ce712-128">Quando emette il token di sicurezza, il servizio STS può specificare l'URI dei servizi Web per cui si desidera usare il token di sicurezza tramite l'aggiunta di una condizione <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ce712-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="ce712-129">Ciò consente all'autenticatore <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servizio Web di destinazione di verificare che il token di sicurezza emesso sia associato a questo servizio Web specificando che questo controllo deve essere svolto mediante l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce712-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="ce712-130">Impostare l'attributo `audienceUriMode` di `<issuedTokenAuthentication>` su <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="ce712-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="ce712-131">Specificare il set di URI validi, aggiungendo gli URI a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="ce712-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="ce712-132">Per altre informazioni, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="ce712-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="ce712-133">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="ce712-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce712-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce712-134">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="ce712-135">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ce712-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="ce712-136">\<add></span><span class="sxs-lookup"><span data-stu-id="ce712-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)  
 [<span data-ttu-id="ce712-137">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ce712-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="ce712-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="ce712-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ce712-139">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="ce712-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
