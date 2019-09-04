---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251883"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="febfe-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="febfe-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="febfe-102">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="febfe-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="febfe-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="febfe-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="febfe-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="febfe-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="febfe-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="febfe-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="febfe-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="febfe-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="febfe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> securityTokenHandlerConfiguration**</span><span class="sxs-lookup"><span data-stu-id="febfe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febfe-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="febfe-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="febfe-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="febfe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="febfe-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="febfe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="febfe-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="febfe-111">Attributes</span></span>  
  
|<span data-ttu-id="febfe-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="febfe-112">Attribute</span></span>|<span data-ttu-id="febfe-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="febfe-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="febfe-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="febfe-114">saveBootstrapContext</span></span>|<span data-ttu-id="febfe-115">Specifica se i token di bootstrap devono essere inclusi nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="febfe-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="febfe-116">Il valore può essere impostato anche in una raccolta di gestori di token impostando l' `saveBootstrapContext` attributo [ \<sull'elemento > IdentityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="febfe-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="febfe-117">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="febfe-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="febfe-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="febfe-118">maximumClockSkew</span></span>|<span data-ttu-id="febfe-119">Oggetto <xref:System.TimeSpan> che specifica lo sfasamento massimo consentito del clock.</span><span class="sxs-lookup"><span data-stu-id="febfe-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="febfe-120">Controlla lo sfasamento massimo consentito di clock quando si eseguono operazioni dipendenti dal tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="febfe-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="febfe-121">Il valore predefinito è 5 minuti, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="febfe-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="febfe-122">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="febfe-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="febfe-123">Lo sfasamento di clock massimo può essere impostato anche a livello di servizio impostando `maximumClockSkew` l'attributo [ \<sull'elemento > IdentityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="febfe-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="febfe-124">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="febfe-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="febfe-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="febfe-125">Child Elements</span></span>  
  
|<span data-ttu-id="febfe-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="febfe-126">Element</span></span>|<span data-ttu-id="febfe-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="febfe-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="febfe-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="febfe-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="febfe-129">Specifica il set di URI che sono identificatori accettabili di questo relying party.</span><span class="sxs-lookup"><span data-stu-id="febfe-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="febfe-130">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-130">Optional.</span></span>|  
|[<span data-ttu-id="febfe-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="febfe-131">\<caches></span></span>](caches.md)|<span data-ttu-id="febfe-132">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="febfe-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="febfe-133">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="febfe-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="febfe-134">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-134">Optional.</span></span>|  
|[<span data-ttu-id="febfe-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="febfe-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="febfe-136">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="febfe-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="febfe-137">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="febfe-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="febfe-138">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="febfe-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="febfe-139">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-139">Optional.</span></span>|  
|[<span data-ttu-id="febfe-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="febfe-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="febfe-141">Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="febfe-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="febfe-142">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-142">Optional.</span></span>|  
|[<span data-ttu-id="febfe-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="febfe-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="febfe-144">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="febfe-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="febfe-145">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="febfe-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="febfe-146">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-146">Optional.</span></span>|  
|[<span data-ttu-id="febfe-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="febfe-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="febfe-148">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="febfe-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="febfe-149">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="febfe-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="febfe-150">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-150">Optional.</span></span>|  
|[<span data-ttu-id="febfe-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="febfe-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="febfe-152">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="febfe-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="febfe-153">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="febfe-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="febfe-154">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="febfe-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="febfe-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="febfe-155">Parent Elements</span></span>  
  
|<span data-ttu-id="febfe-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="febfe-156">Element</span></span>|<span data-ttu-id="febfe-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="febfe-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="febfe-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="febfe-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="febfe-159">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="febfe-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="febfe-160">Note</span><span class="sxs-lookup"><span data-stu-id="febfe-160">Remarks</span></span>  
 <span data-ttu-id="febfe-161">In questa sezione vengono forniti i valori <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> delle proprietà per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="febfe-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="febfe-162">Le impostazioni configurate in questa sezione eseguono l'override di quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="febfe-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="febfe-163">Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="febfe-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="febfe-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="febfe-164">Example</span></span>  
  
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
