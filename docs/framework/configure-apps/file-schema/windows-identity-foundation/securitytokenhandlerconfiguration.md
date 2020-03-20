---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152567"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="d51e8-101">\<> securityTokenHandlerConfiguration</span><span class="sxs-lookup"><span data-stu-id="d51e8-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="d51e8-102">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="d51e8-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d51e8-104">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d51e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d51e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d51e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>securityTokenHandlerConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d51e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d51e8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d51e8-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d51e8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d51e8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d51e8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d51e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d51e8-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="d51e8-111">Attributes</span></span>  
  
|<span data-ttu-id="d51e8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d51e8-112">Attribute</span></span>|<span data-ttu-id="d51e8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d51e8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d51e8-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="d51e8-114">saveBootstrapContext</span></span>|<span data-ttu-id="d51e8-115">Specifica se i token di bootstrap devono essere inclusi nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="d51e8-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="d51e8-116">Il valore può anche essere impostato su `saveBootstrapContext` una raccolta di gestori di token impostando l'attributo sull'elemento [ \<di>identityConfiguration.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="d51e8-117">Un valore impostato nella raccolta di gestori di token esegue l'override del valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d51e8-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="d51e8-118">maximumClockSkew (massimoClockSkew)</span><span class="sxs-lookup"><span data-stu-id="d51e8-118">maximumClockSkew</span></span>|<span data-ttu-id="d51e8-119">Oggetto <xref:System.TimeSpan> che specifica l'inclinazione massima consentita.</span><span class="sxs-lookup"><span data-stu-id="d51e8-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="d51e8-120">Controlla l'asimmetria di clock massima consentita durante l'esecuzione di operazioni sensibili al tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="d51e8-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="d51e8-121">Il valore predefinito è 5 minuti, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="d51e8-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="d51e8-122">Per ulteriori informazioni su <xref:System.TimeSpan> come specificare i valori, vedere [Valori Di intervallo](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d51e8-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="d51e8-123">L'asimmetria di clock massima può essere `maximumClockSkew` impostata anche a livello di servizio impostando l'attributo sull'elemento [ \<identityConfiguration>.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d51e8-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="d51e8-124">Un valore impostato nella raccolta di gestori di token esegue l'override del valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d51e8-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d51e8-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d51e8-125">Child Elements</span></span>  
  
|<span data-ttu-id="d51e8-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="d51e8-126">Element</span></span>|<span data-ttu-id="d51e8-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d51e8-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d51e8-128">\<AudienceUris></span><span class="sxs-lookup"><span data-stu-id="d51e8-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="d51e8-129">Specifica il set di URI che sono identificatori accettabili di questa relying party.</span><span class="sxs-lookup"><span data-stu-id="d51e8-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="d51e8-130">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-130">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-131">\<>nella cache</span><span class="sxs-lookup"><span data-stu-id="d51e8-131">\<caches></span></span>](caches.md)|<span data-ttu-id="d51e8-132">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione di token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="d51e8-133">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d51e8-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d51e8-134">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-134">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-135">\<certificateConvalida></span><span class="sxs-lookup"><span data-stu-id="d51e8-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="d51e8-136">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="d51e8-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="d51e8-137">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d51e8-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d51e8-138">Queste impostazioni vengono sottoposte a override se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="d51e8-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="d51e8-139">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-139">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-140">\<IssuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d51e8-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="d51e8-141">Configura il registro del nome dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d51e8-142">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-142">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d51e8-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="d51e8-144">Registra il resolver di token dell'autorità di certificazione utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d51e8-145">Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d51e8-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="d51e8-146">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-146">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d51e8-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="d51e8-148">Registra il resolver di token del servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d51e8-149">Il resolver del token del servizio viene utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d51e8-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="d51e8-150">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-150">Optional.</span></span>|  
|[<span data-ttu-id="d51e8-151">\<>di tokenReplayDetection</span><span class="sxs-lookup"><span data-stu-id="d51e8-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="d51e8-152">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="d51e8-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="d51e8-153">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d51e8-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d51e8-154">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d51e8-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d51e8-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d51e8-155">Parent Elements</span></span>  
  
|<span data-ttu-id="d51e8-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="d51e8-156">Element</span></span>|<span data-ttu-id="d51e8-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d51e8-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d51e8-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d51e8-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d51e8-159">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d51e8-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d51e8-160">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d51e8-160">Remarks</span></span>  
 <span data-ttu-id="d51e8-161">In questa sezione vengono <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> forniti i valori delle proprietà per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d51e8-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="d51e8-162">Le impostazioni configurate in questa sezione sostituiscono quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d51e8-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="d51e8-163">Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d51e8-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d51e8-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="d51e8-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
