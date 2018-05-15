---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="02cb4-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="02cb4-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="02cb4-103">Consente di configurare il Registro di sistema nome dell'autorità di certificazione che viene utilizzata dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="02cb4-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="02cb4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="02cb4-104">\<system.identityModel></span></span>  
<span data-ttu-id="02cb4-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="02cb4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="02cb4-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="02cb4-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="02cb4-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="02cb4-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="02cb4-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="02cb4-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02cb4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02cb4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02cb4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02cb4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="02cb4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02cb4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02cb4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="02cb4-112">Attributes</span></span>  
  
|<span data-ttu-id="02cb4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="02cb4-113">Attribute</span></span>|<span data-ttu-id="02cb4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02cb4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02cb4-115">tipo</span><span class="sxs-lookup"><span data-stu-id="02cb4-115">type</span></span>|<span data-ttu-id="02cb4-116">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="02cb4-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="02cb4-117">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="02cb4-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02cb4-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02cb4-118">Child Elements</span></span>  
  
|<span data-ttu-id="02cb4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="02cb4-119">Element</span></span>|<span data-ttu-id="02cb4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02cb4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02cb4-121">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="02cb4-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="02cb4-122">Quando il `type` attributo specifica il Registro di sistema di nome dell'autorità di certificazione basata sulla configurazione (il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="02cb4-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="02cb4-123">Il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) può richiedere l'elemento `<add>`, `<clear>`, o `<remove>` elementi come elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="02cb4-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02cb4-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02cb4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="02cb4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="02cb4-125">Element</span></span>|<span data-ttu-id="02cb4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02cb4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02cb4-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="02cb4-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="02cb4-128">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="02cb4-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02cb4-129">Note</span><span class="sxs-lookup"><span data-stu-id="02cb4-129">Remarks</span></span>  
 <span data-ttu-id="02cb4-130">Tutti i token dell'autorità di certificazione vengono convalidati mediante un registro di sistema di nome dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="02cb4-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="02cb4-131">Si tratta di un oggetto da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="02cb4-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="02cb4-132">Il Registro di sistema di nome dell'autorità di certificazione viene utilizzato per associare un nome di tasti di scelta rapida per il materiale di crittografia è necessaria per verificare le firme di token generato dall'emittente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="02cb4-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="02cb4-133">Il Registro di sistema di nome dell'autorità emittente mantiene un elenco delle autorità emittenti attendibili per l'applicazione relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="02cb4-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="02cb4-134">Il tipo del Registro di sistema di nome dell'autorità di certificazione è specificato utilizzando il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="02cb4-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="02cb4-135">Il `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="02cb4-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="02cb4-136">Fornire la logica che elabora gli elementi figlio, eseguendo l'override di <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="02cb4-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="02cb4-137">WIF offre una singola autorità di certificazione come nome del Registro di sistema predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="02cb4-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="02cb4-138">Questa classe Usa un set di autorità emittenti attendibili i certificati che sono specificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="02cb4-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="02cb4-139">Richiede un elemento di configurazione figlio, `<trustedIssuers>`, in cui viene configurato l'insieme dei certificati dell'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="02cb4-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="02cb4-140">Attendibili i certificati vengono specificati utilizzando l'ASN. 1 formato dell'identificazione digitale del certificato con codifica e viene aggiunti o rimossi dalla raccolta utilizzando `<add>`, `<clear>`, o `<remove>` elementi.</span><span class="sxs-lookup"><span data-stu-id="02cb4-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="02cb4-141">Il `<issuerNameRegistry>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.</span><span class="sxs-lookup"><span data-stu-id="02cb4-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02cb4-142">Specifica il `<issuerNameRegistry>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="02cb4-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="02cb4-143">Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="02cb4-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02cb4-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="02cb4-144">Example</span></span>  
 <span data-ttu-id="02cb4-145">Il codice XML seguente viene illustrato come specificare l'autorità emittente di base di configurazione del Registro di sistema di nome.</span><span class="sxs-lookup"><span data-stu-id="02cb4-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02cb4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02cb4-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
