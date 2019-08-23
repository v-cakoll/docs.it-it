---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942451"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="1495d-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1495d-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="1495d-102">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1495d-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="1495d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1495d-103">\<system.identityModel></span></span>  
<span data-ttu-id="1495d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1495d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1495d-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1495d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1495d-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1495d-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1495d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1495d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1495d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1495d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1495d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1495d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1495d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1495d-110">Attributes</span></span>  
  
|<span data-ttu-id="1495d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1495d-111">Attribute</span></span>|<span data-ttu-id="1495d-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1495d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1495d-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="1495d-113">saveBootstrapContext</span></span>|<span data-ttu-id="1495d-114">Specifica se i token di bootstrap devono essere inclusi nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="1495d-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="1495d-115">Il valore può essere impostato anche in una raccolta di gestori di token impostando l' `saveBootstrapContext` attributo [ \<sull'elemento > IdentityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="1495d-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="1495d-116">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="1495d-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="1495d-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="1495d-117">maximumClockSkew</span></span>|<span data-ttu-id="1495d-118">Oggetto <xref:System.TimeSpan> che specifica lo sfasamento massimo consentito del clock.</span><span class="sxs-lookup"><span data-stu-id="1495d-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="1495d-119">Controlla lo sfasamento massimo consentito di clock quando si eseguono operazioni dipendenti dal tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="1495d-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="1495d-120">Il valore predefinito è 5 minuti, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="1495d-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="1495d-121">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1495d-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="1495d-122">Lo sfasamento di clock massimo può essere impostato anche a livello di servizio impostando `maximumClockSkew` l'attributo [ \<sull'elemento > IdentityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="1495d-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="1495d-123">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="1495d-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1495d-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1495d-124">Child Elements</span></span>  
  
|<span data-ttu-id="1495d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1495d-125">Element</span></span>|<span data-ttu-id="1495d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1495d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1495d-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="1495d-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="1495d-128">Specifica il set di URI che sono identificatori accettabili di questo relying party.</span><span class="sxs-lookup"><span data-stu-id="1495d-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="1495d-129">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-129">Optional.</span></span>|  
|[<span data-ttu-id="1495d-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="1495d-130">\<caches></span></span>](caches.md)|<span data-ttu-id="1495d-131">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="1495d-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="1495d-132">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1495d-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="1495d-133">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-133">Optional.</span></span>|  
|[<span data-ttu-id="1495d-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="1495d-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="1495d-135">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="1495d-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="1495d-136">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1495d-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="1495d-137">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="1495d-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="1495d-138">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-138">Optional.</span></span>|  
|[<span data-ttu-id="1495d-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="1495d-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="1495d-140">Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1495d-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1495d-141">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-141">Optional.</span></span>|  
|[<span data-ttu-id="1495d-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1495d-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="1495d-143">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1495d-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1495d-144">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="1495d-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="1495d-145">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-145">Optional.</span></span>|  
|[<span data-ttu-id="1495d-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1495d-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="1495d-147">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1495d-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1495d-148">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="1495d-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="1495d-149">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-149">Optional.</span></span>|  
|[<span data-ttu-id="1495d-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="1495d-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="1495d-151">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="1495d-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="1495d-152">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1495d-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="1495d-153">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1495d-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1495d-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1495d-154">Parent Elements</span></span>  
  
|<span data-ttu-id="1495d-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="1495d-155">Element</span></span>|<span data-ttu-id="1495d-156">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1495d-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1495d-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1495d-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="1495d-158">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1495d-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1495d-159">Note</span><span class="sxs-lookup"><span data-stu-id="1495d-159">Remarks</span></span>  
 <span data-ttu-id="1495d-160">In questa sezione vengono forniti i valori <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> delle proprietà per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1495d-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="1495d-161">Le impostazioni configurate in questa sezione eseguono l'override di quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="1495d-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="1495d-162">Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1495d-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1495d-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="1495d-163">Example</span></span>  
  
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
