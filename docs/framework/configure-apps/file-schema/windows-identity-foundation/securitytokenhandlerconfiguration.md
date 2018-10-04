---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793279"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="8c584-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="8c584-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="8c584-103">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8c584-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="8c584-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8c584-104">\<system.identityModel></span></span>  
<span data-ttu-id="8c584-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8c584-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8c584-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8c584-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8c584-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8c584-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c584-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c584-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c584-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c584-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c584-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c584-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c584-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c584-111">Attributes</span></span>  
  
|<span data-ttu-id="8c584-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8c584-112">Attribute</span></span>|<span data-ttu-id="8c584-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c584-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c584-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="8c584-114">saveBootstrapContext</span></span>|<span data-ttu-id="8c584-115">Specifica se i token di bootstrap devono essere incluse nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="8c584-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="8c584-116">Il valore può anche essere impostato su una raccolta di gestori di token impostando il `saveBootstrapContext` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8c584-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="8c584-117">Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8c584-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="8c584-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="8c584-118">maximumClockSkew</span></span>|<span data-ttu-id="8c584-119">Oggetto <xref:System.TimeSpan> che specifica il numero massimo consentito sfasamenti di orario.</span><span class="sxs-lookup"><span data-stu-id="8c584-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="8c584-120">Controlla il numero massimo consentito sfasamenti di orario durante l'esecuzione di operazioni di tempo, ad esempio convalida la data di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="8c584-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="8c584-121">Il valore predefinito è di 5 minuti "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="8c584-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="8c584-122">Per altre informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c584-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="8c584-123">La differenza di orario massimo può essere impostato anche a livello di servizio impostando il `maximumClockSkew` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8c584-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="8c584-124">Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8c584-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c584-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c584-125">Child Elements</span></span>  
  
|<span data-ttu-id="8c584-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c584-126">Element</span></span>|<span data-ttu-id="8c584-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c584-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c584-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="8c584-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="8c584-129">Specifica il set di URI accettabili identificatori di questa relying party.</span><span class="sxs-lookup"><span data-stu-id="8c584-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="8c584-130">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-130">Optional.</span></span>|  
|[<span data-ttu-id="8c584-131">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="8c584-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="8c584-132">Registra le cache usate per il rilevamento riproduzione token e i token di sessione.</span><span class="sxs-lookup"><span data-stu-id="8c584-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="8c584-133">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c584-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c584-134">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-134">Optional.</span></span>|  
|[<span data-ttu-id="8c584-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="8c584-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="8c584-136">Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="8c584-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="8c584-137">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c584-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c584-138">Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="8c584-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="8c584-139">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-139">Optional.</span></span>|  
|[<span data-ttu-id="8c584-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="8c584-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="8c584-141">Configura il registro dei nomi dell'autorità di certificazione che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8c584-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c584-142">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-142">Optional.</span></span>|  
|[<span data-ttu-id="8c584-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8c584-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="8c584-144">Registra il resolver dei token che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8c584-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c584-145">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="8c584-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="8c584-146">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-146">Optional.</span></span>|  
|[<span data-ttu-id="8c584-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8c584-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="8c584-148">Registra il resolver dei token di servizio che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8c584-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c584-149">Il resolver dei token di servizio viene usato per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="8c584-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="8c584-150">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-150">Optional.</span></span>|  
|[<span data-ttu-id="8c584-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="8c584-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="8c584-152">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="8c584-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="8c584-153">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c584-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c584-154">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c584-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c584-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c584-155">Parent Elements</span></span>  
  
|<span data-ttu-id="8c584-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c584-156">Element</span></span>|<span data-ttu-id="8c584-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c584-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c584-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8c584-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="8c584-159">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8c584-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c584-160">Note</span><span class="sxs-lookup"><span data-stu-id="8c584-160">Remarks</span></span>  
 <span data-ttu-id="8c584-161">In questa sezione fornisce valori di proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8c584-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="8c584-162">Impostazioni configurate in questa sezione sostituiranno quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8c584-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="8c584-163">Alcune di queste impostazioni possono, a sua volta, eseguire l'override dalle impostazioni che vengono specificate quando viene aggiunto un gestore per la raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c584-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c584-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c584-164">Example</span></span>  
  
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
