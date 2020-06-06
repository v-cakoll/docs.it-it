---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152567"
---
# \<securityTokenHandlerConfiguration>
<span data-ttu-id="9c606-101">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9c606-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="9c606-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c606-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c606-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c606-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9c606-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c606-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c606-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c606-105">Attributes</span></span>  
  
|<span data-ttu-id="9c606-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="9c606-106">Attribute</span></span>|<span data-ttu-id="9c606-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c606-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c606-108">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="9c606-108">saveBootstrapContext</span></span>|<span data-ttu-id="9c606-109">Specifica se i token di bootstrap devono essere inclusi nel token di sessione.</span><span class="sxs-lookup"><span data-stu-id="9c606-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="9c606-110">Il valore può essere impostato anche in una raccolta di gestori di token impostando l' `saveBootstrapContext` attributo sull' [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9c606-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9c606-111">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9c606-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="9c606-112">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="9c606-112">maximumClockSkew</span></span>|<span data-ttu-id="9c606-113">Oggetto <xref:System.TimeSpan> che specifica lo sfasamento massimo consentito del clock.</span><span class="sxs-lookup"><span data-stu-id="9c606-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="9c606-114">Controlla lo sfasamento massimo consentito di clock quando si eseguono operazioni dipendenti dal tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="9c606-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="9c606-115">Il valore predefinito è 5 minuti, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="9c606-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="9c606-116">Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9c606-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="9c606-117">Lo sfasamento di clock massimo può essere impostato anche a livello di servizio impostando l' `maximumClockSkew` attributo sull' [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9c606-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9c606-118">Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9c606-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c606-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c606-119">Child Elements</span></span>  
  
|<span data-ttu-id="9c606-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c606-120">Element</span></span>|<span data-ttu-id="9c606-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c606-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="9c606-122">Specifica il set di URI che sono identificatori accettabili di questo relying party.</span><span class="sxs-lookup"><span data-stu-id="9c606-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="9c606-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="9c606-124">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="9c606-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="9c606-125">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c606-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9c606-126">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="9c606-127">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="9c606-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="9c606-128">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c606-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9c606-129">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="9c606-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="9c606-130">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="9c606-131">Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9c606-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9c606-132">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="9c606-133">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9c606-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9c606-134">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9c606-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="9c606-135">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="9c606-136">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9c606-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9c606-137">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9c606-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="9c606-138">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="9c606-139">Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="9c606-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="9c606-140">Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c606-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9c606-141">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9c606-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c606-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c606-142">Parent Elements</span></span>  
  
|<span data-ttu-id="9c606-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c606-143">Element</span></span>|<span data-ttu-id="9c606-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c606-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="9c606-145">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9c606-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c606-146">Commenti</span><span class="sxs-lookup"><span data-stu-id="9c606-146">Remarks</span></span>  
 <span data-ttu-id="9c606-147">In questa sezione vengono forniti i valori delle proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9c606-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="9c606-148">Le impostazioni configurate in questa sezione eseguono l'override di quelle configurate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="9c606-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="9c606-149">Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c606-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c606-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c606-150">Example</span></span>  
  
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
