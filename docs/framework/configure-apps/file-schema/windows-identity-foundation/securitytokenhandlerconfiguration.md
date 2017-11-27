---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: be98c93452c9c7a37ecad5b03f5160ea08f2c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="b6548-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="b6548-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="b6548-103">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b6548-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="b6548-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="b6548-104">\<system.identityModel></span></span>  
<span data-ttu-id="b6548-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b6548-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b6548-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b6548-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b6548-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b6548-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6548-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6548-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6548-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6548-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6548-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6548-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6548-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6548-111">Attributes</span></span>  
  
|<span data-ttu-id="b6548-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6548-112">Attribute</span></span>|<span data-ttu-id="b6548-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6548-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6548-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="b6548-114">saveBootstrapContext</span></span>|<span data-ttu-id="b6548-115">Specifica se i token di bootstrap devono essere inclusi nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="b6548-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="b6548-116">Il valore può inoltre essere impostato su una raccolta di gestore del token impostando il `saveBootstrapContext` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b6548-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="b6548-117">Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b6548-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="b6548-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="b6548-118">maximumClockSkew</span></span>|<span data-ttu-id="b6548-119">Oggetto <xref:System.TimeSpan> che specifica l'inclinazione di clock massima.</span><span class="sxs-lookup"><span data-stu-id="b6548-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="b6548-120">Controlla lo sfasamento dei segnali di clock massima per le operazioni di scadenza, ad esempio convalida l'ora di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6548-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="b6548-121">Il valore predefinito è 5 minuti, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="b6548-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="b6548-122">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="b6548-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="b6548-123">Lo sfasamento dei segnali di clock massima può essere impostato anche a livello di servizio mediante l'impostazione di `maximumClockSkew` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b6548-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="b6548-124">Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b6548-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6548-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6548-125">Child Elements</span></span>  
  
|<span data-ttu-id="b6548-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6548-126">Element</span></span>|<span data-ttu-id="b6548-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6548-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6548-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="b6548-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="b6548-129">Specifica il set di URI accettabili identificatori delle relying party.</span><span class="sxs-lookup"><span data-stu-id="b6548-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="b6548-130">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-130">Optional.</span></span>|  
|[<span data-ttu-id="b6548-131">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="b6548-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="b6548-132">Registra le cache usate per i token di sessione e il rilevamento riproduzione token.</span><span class="sxs-lookup"><span data-stu-id="b6548-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="b6548-133">È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6548-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b6548-134">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-134">Optional.</span></span>|  
|[<span data-ttu-id="b6548-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="b6548-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="b6548-136">Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="b6548-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="b6548-137">È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6548-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b6548-138">Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio servizio di convalida.</span><span class="sxs-lookup"><span data-stu-id="b6548-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="b6548-139">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-139">Optional.</span></span>|  
|[<span data-ttu-id="b6548-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="b6548-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="b6548-141">Consente di configurare il Registro di sistema nome dell'autorità di certificazione che viene utilizzata dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b6548-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b6548-142">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-142">Optional.</span></span>|  
|[<span data-ttu-id="b6548-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b6548-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="b6548-144">Registra il resolver del token dell'autorità di certificazione che viene utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b6548-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b6548-145">Il resolver del token dell'autorità di certificazione viene utilizzato per risolvere il token di firma di token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="b6548-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b6548-146">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-146">Optional.</span></span>|  
|[<span data-ttu-id="b6548-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b6548-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="b6548-148">Registra il resolver dei token di servizio che viene utilizzata dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b6548-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b6548-149">Il resolver dei token di servizio viene utilizzato per risolvere il token di crittografia di token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="b6548-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b6548-150">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-150">Optional.</span></span>|  
|[<span data-ttu-id="b6548-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="b6548-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="b6548-152">Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="b6548-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="b6548-153">È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6548-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b6548-154">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6548-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6548-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6548-155">Parent Elements</span></span>  
  
|<span data-ttu-id="b6548-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6548-156">Element</span></span>|<span data-ttu-id="b6548-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6548-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6548-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b6548-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="b6548-159">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6548-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6548-160">Note</span><span class="sxs-lookup"><span data-stu-id="b6548-160">Remarks</span></span>  
 <span data-ttu-id="b6548-161">In questa sezione fornisce i valori delle proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b6548-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="b6548-162">Le impostazioni configurate in questa sezione sostituiscono quelli configurati nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b6548-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="b6548-163">Alcune di queste impostazioni possono, a sua volta, eseguire l'override delle impostazioni specificate quando si aggiunge un gestore per la raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6548-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6548-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6548-164">Example</span></span>  
  
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
