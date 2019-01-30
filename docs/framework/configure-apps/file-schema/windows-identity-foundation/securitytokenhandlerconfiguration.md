---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262887"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="6e3f1-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6e3f1-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="6e3f1-102">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="6e3f1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6e3f1-103">\<system.identityModel></span></span>  
<span data-ttu-id="6e3f1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6e3f1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6e3f1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6e3f1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6e3f1-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6e3f1-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3f1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e3f1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e3f1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6e3f1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e3f1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e3f1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6e3f1-110">Attributes</span></span>  
  
|<span data-ttu-id="6e3f1-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6e3f1-111">Attribute</span></span>|<span data-ttu-id="6e3f1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e3f1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e3f1-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="6e3f1-113">saveBootstrapContext</span></span>|<span data-ttu-id="6e3f1-114">Specifica se i token di bootstrap devono essere incluse nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="6e3f1-115">Il valore può anche essere impostato su una raccolta di gestori di token impostando il `saveBootstrapContext` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6e3f1-116">Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="6e3f1-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="6e3f1-117">maximumClockSkew</span></span>|<span data-ttu-id="6e3f1-118">Oggetto <xref:System.TimeSpan> che specifica il numero massimo consentito sfasamenti di orario.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="6e3f1-119">Controlla il numero massimo consentito sfasamenti di orario durante l'esecuzione di operazioni di tempo, ad esempio convalida la data di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="6e3f1-120">Il valore predefinito è di 5 minuti "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="6e3f1-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="6e3f1-121">Per altre informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6e3f1-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="6e3f1-122">La differenza di orario massimo può essere impostato anche a livello di servizio impostando il `maximumClockSkew` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6e3f1-123">Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e3f1-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6e3f1-124">Child Elements</span></span>  
  
|<span data-ttu-id="6e3f1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e3f1-125">Element</span></span>|<span data-ttu-id="6e3f1-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e3f1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e3f1-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="6e3f1-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="6e3f1-128">Specifica il set di URI accettabili identificatori di questa relying party.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="6e3f1-129">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-129">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="6e3f1-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="6e3f1-131">Registra le cache usate per il rilevamento riproduzione token e i token di sessione.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="6e3f1-132">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6e3f1-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-133">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6e3f1-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="6e3f1-135">Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6e3f1-136">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6e3f1-137">Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="6e3f1-138">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-138">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="6e3f1-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="6e3f1-140">Configura il registro dei nomi dell'autorità di certificazione che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6e3f1-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-141">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6e3f1-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="6e3f1-143">Registra il resolver dei token che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6e3f1-144">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6e3f1-145">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-145">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6e3f1-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="6e3f1-147">Registra il resolver dei token di servizio che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6e3f1-148">Il resolver dei token di servizio viene usato per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6e3f1-149">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-149">Optional.</span></span>|  
|[<span data-ttu-id="6e3f1-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="6e3f1-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="6e3f1-151">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="6e3f1-152">Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6e3f1-153">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e3f1-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6e3f1-154">Parent Elements</span></span>  
  
|<span data-ttu-id="6e3f1-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e3f1-155">Element</span></span>|<span data-ttu-id="6e3f1-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e3f1-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e3f1-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6e3f1-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="6e3f1-158">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e3f1-159">Note</span><span class="sxs-lookup"><span data-stu-id="6e3f1-159">Remarks</span></span>  
 <span data-ttu-id="6e3f1-160">In questa sezione fornisce valori di proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="6e3f1-161">Impostazioni configurate in questa sezione sostituiranno quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="6e3f1-162">Alcune di queste impostazioni possono, a sua volta, eseguire l'override dalle impostazioni che vengono specificate quando viene aggiunto un gestore per la raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6e3f1-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3f1-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e3f1-163">Example</span></span>  
  
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
