---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: d079c0a03f0c88bab04e3fe2e857e0be4d3af11e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283608"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="e6300-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="e6300-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="e6300-102">Rappresenta una raccolta di URI di destinazione ai quali può essere destinato il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6300-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="e6300-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e6300-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6300-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e6300-104">\<behaviors></span></span>  
<span data-ttu-id="e6300-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e6300-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e6300-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e6300-106">\<behavior></span></span>  
<span data-ttu-id="e6300-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="e6300-107">\<serviceCredentials></span></span>  
<span data-ttu-id="e6300-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e6300-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="e6300-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="e6300-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6300-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6300-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6300-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e6300-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e6300-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e6300-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6300-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e6300-113">Attributes</span></span>  
 <span data-ttu-id="e6300-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e6300-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6300-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6300-115">Child Elements</span></span>  
  
|<span data-ttu-id="e6300-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6300-116">Element</span></span>|<span data-ttu-id="e6300-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6300-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6300-118">\<add></span><span class="sxs-lookup"><span data-stu-id="e6300-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="e6300-119">Aggiunge un URI di destinazione al quale il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6300-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6300-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e6300-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e6300-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6300-121">Element</span></span>|<span data-ttu-id="e6300-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6300-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6300-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e6300-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e6300-124">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="e6300-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6300-125">Note</span><span class="sxs-lookup"><span data-stu-id="e6300-125">Remarks</span></span>  
 <span data-ttu-id="e6300-126">Usare questa raccolta in un'applicazione federata che usa un servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="e6300-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="e6300-127">Quando emette il token di sicurezza, il servizio STS può specificare l'URI dei servizi Web per cui si desidera usare il token di sicurezza tramite l'aggiunta di una condizione <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e6300-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="e6300-128">Ciò consente all'autenticatore <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servizio Web di destinazione di verificare che il token di sicurezza emesso sia associato a questo servizio Web specificando che questo controllo deve essere svolto mediante l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6300-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="e6300-129">Impostare l'attributo `audienceUriMode` di `<issuedTokenAuthentication>` su <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="e6300-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="e6300-130">Specificare il set di URI validi, aggiungendo gli URI a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6300-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="e6300-131">Per altre informazioni, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6300-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="e6300-132">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="e6300-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6300-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6300-133">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="e6300-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e6300-134">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="e6300-135">\<add></span><span class="sxs-lookup"><span data-stu-id="e6300-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)
- [<span data-ttu-id="e6300-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6300-136">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e6300-137">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e6300-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e6300-138">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="e6300-138">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
