---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: ea2d4bb285047939992e9b191abc2dc896bdaa6a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398279"
---
# \<allowedAudienceUris>
<span data-ttu-id="e4db5-101">Rappresenta una raccolta di URI di destinazione ai quali può essere destinato il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-101">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowedAudienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="e4db5-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4db5-102">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4db5-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e4db5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e4db5-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e4db5-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4db5-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="e4db5-105">Attributes</span></span>  
 <span data-ttu-id="e4db5-106">No.</span><span class="sxs-lookup"><span data-stu-id="e4db5-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4db5-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e4db5-107">Child Elements</span></span>  
  
|<span data-ttu-id="e4db5-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4db5-108">Element</span></span>|<span data-ttu-id="e4db5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4db5-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-allowedaudienceuris.md)|<span data-ttu-id="e4db5-110">Aggiunge un URI di destinazione al quale il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-110">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4db5-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e4db5-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e4db5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4db5-112">Element</span></span>|<span data-ttu-id="e4db5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4db5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e4db5-114">Specifica un token emesso da una credenziale del servizio.</span><span class="sxs-lookup"><span data-stu-id="e4db5-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4db5-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="e4db5-115">Remarks</span></span>  
 <span data-ttu-id="e4db5-116">Usare questa raccolta in un'applicazione federata che usa un servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-116">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="e4db5-117">Quando emette il token di sicurezza, il servizio STS può specificare l'URI dei servizi Web per cui si desidera usare il token di sicurezza tramite l'aggiunta di una condizione <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e4db5-117">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="e4db5-118">Ciò consente all'autenticatore <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servizio Web di destinazione di verificare che il token di sicurezza emesso sia associato a questo servizio Web specificando che questo controllo deve essere svolto mediante l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4db5-118">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="e4db5-119">Impostare l'attributo `audienceUriMode` di `<issuedTokenAuthentication>` su <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-119">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="e4db5-120">Specificare il set di URI validi, aggiungendo gli URI a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="e4db5-120">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="e4db5-121">Per altre informazioni, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-121">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="e4db5-122">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="e4db5-122">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4db5-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e4db5-123">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [\<add>](add-of-allowedaudienceuris.md)
- [<span data-ttu-id="e4db5-124">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4db5-124">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e4db5-125">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="e4db5-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e4db5-126">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="e4db5-126">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
