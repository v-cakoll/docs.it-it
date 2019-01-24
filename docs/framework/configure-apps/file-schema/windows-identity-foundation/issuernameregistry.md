---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: f23f0103e228bc23a06a3ff0e0c5c2a12bdae73f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748103"
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="d41d2-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d2-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="d41d2-103">Configura il registro dei nomi dell'autorità di certificazione che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d41d2-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="d41d2-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d41d2-104">\<system.identityModel></span></span>  
<span data-ttu-id="d41d2-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d41d2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d41d2-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d41d2-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d41d2-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d41d2-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d41d2-108">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d41d2-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41d2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d41d2-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d41d2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d41d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d41d2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d41d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d41d2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d41d2-112">Attributes</span></span>  
  
|<span data-ttu-id="d41d2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d41d2-113">Attribute</span></span>|<span data-ttu-id="d41d2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d41d2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d41d2-115">tipo</span><span class="sxs-lookup"><span data-stu-id="d41d2-115">type</span></span>|<span data-ttu-id="d41d2-116">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="d41d2-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d41d2-117">Per altre informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="d41d2-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d41d2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d41d2-118">Child Elements</span></span>  
  
|<span data-ttu-id="d41d2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d41d2-119">Element</span></span>|<span data-ttu-id="d41d2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d41d2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d41d2-121">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d41d2-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="d41d2-122">Quando la `type` attributo specifica il registro dei nomi basato sulla configurazione dell'autorità emittente (il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="d41d2-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="d41d2-123">Il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento può accettare `<add>`, `<clear>`, o `<remove>` elementi come elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="d41d2-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d41d2-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d41d2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d41d2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d41d2-125">Element</span></span>|<span data-ttu-id="d41d2-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d41d2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d41d2-127">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d41d2-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d41d2-128">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d41d2-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d41d2-129">Note</span><span class="sxs-lookup"><span data-stu-id="d41d2-129">Remarks</span></span>  
 <span data-ttu-id="d41d2-130">Tutti i token dell'autorità di certificazione vengono convalidati tramite un registro dei nomi dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d41d2-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="d41d2-131">Si tratta di un oggetto da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="d41d2-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d41d2-132">Il registro dei nomi dell'autorità di certificazione viene utilizzato per associare un nome mnemonico al materiale di crittografia che è necessario per verificare le firme dei token prodotti dall'autorità emittente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d41d2-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="d41d2-133">Il registro dei nomi dell'autorità emittente mantiene un elenco di autorità di certificazione considerate attendibili dall'applicazione relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="d41d2-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="d41d2-134">Il tipo del Registro di sistema di nome dell'autorità di certificazione è specificato utilizzando il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="d41d2-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="d41d2-135">Il `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d41d2-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="d41d2-136">Fornire la logica che elabora tali elementi figlio eseguendo l'override di <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="d41d2-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="d41d2-137">WIF fornisce una singola autorità di certificazione nome tipo del Registro di sistema per impostazione predefinita, il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="d41d2-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d41d2-138">Questa classe Usa un set di certificati di autorità emittenti attendibili che sono specificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="d41d2-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="d41d2-139">Richiede un elemento di configurazione figlio, `<trustedIssuers>`, in cui viene configurato l'insieme di certificati di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="d41d2-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="d41d2-140">Attendibili i certificati vengono specificati usando il ASN.1 formato dell'identificazione digitale del certificato con codifica e viene aggiunti o rimossi dalla raccolta utilizzando `<add>`, `<clear>`, o `<remove>` elementi.</span><span class="sxs-lookup"><span data-stu-id="d41d2-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d41d2-141">Il `<issuerNameRegistry>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.</span><span class="sxs-lookup"><span data-stu-id="d41d2-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d41d2-142">Specifica la `<issuerNameRegistry>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d41d2-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d41d2-143">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d41d2-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d41d2-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="d41d2-144">Example</span></span>  
 <span data-ttu-id="d41d2-145">Il codice XML seguente viene illustrato come specificare l'autorità di certificazione di base di configurazione del registro dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d41d2-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d41d2-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d41d2-146">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
