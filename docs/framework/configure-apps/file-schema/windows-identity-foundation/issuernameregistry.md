---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942673"
---
# <a name="issuernameregistry"></a><span data-ttu-id="af931-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="af931-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="af931-102">Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="af931-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="af931-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="af931-103">\<system.identityModel></span></span>  
<span data-ttu-id="af931-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="af931-104">\<identityConfiguration></span></span>  
<span data-ttu-id="af931-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="af931-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="af931-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="af931-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="af931-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="af931-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af931-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af931-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af931-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af931-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af931-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af931-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af931-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="af931-111">Attributes</span></span>  
  
|<span data-ttu-id="af931-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="af931-112">Attribute</span></span>|<span data-ttu-id="af931-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="af931-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af931-114">type</span><span class="sxs-lookup"><span data-stu-id="af931-114">type</span></span>|<span data-ttu-id="af931-115">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="af931-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="af931-116">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="af931-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af931-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af931-117">Child Elements</span></span>  
  
|<span data-ttu-id="af931-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="af931-118">Element</span></span>|<span data-ttu-id="af931-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af931-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af931-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="af931-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="af931-121">Quando l' `type` attributo specifica il registro dei nomi delle autorità emittenti basato sulla configurazione <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (la classe), è necessario specificare l' [ \<elemento > TrustedIssuers](trustedissuers.md) .</span><span class="sxs-lookup"><span data-stu-id="af931-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="af931-122">L' `<add>` `<clear>` [ \<elemento > TrustedIssuers](trustedissuers.md) può assumere elementi, o `<remove>` come elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="af931-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af931-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af931-123">Parent Elements</span></span>  
  
|<span data-ttu-id="af931-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="af931-124">Element</span></span>|<span data-ttu-id="af931-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af931-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af931-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="af931-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="af931-127">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="af931-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af931-128">Note</span><span class="sxs-lookup"><span data-stu-id="af931-128">Remarks</span></span>  
 <span data-ttu-id="af931-129">Tutti i token dell'autorità emittente vengono convalidati utilizzando un registro di sistema del nome dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="af931-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="af931-130">Si tratta di un oggetto che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="af931-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="af931-131">Il registro dei nomi delle autorità emittenti viene utilizzato per associare un nome mnemonico al materiale crittografico necessario per verificare le firme dei token prodotti dall'emittente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="af931-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="af931-132">Il registro dei nomi delle autorità emittenti gestisce un elenco di autorità di certificazione ritenute attendibili dall'applicazione relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="af931-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="af931-133">Il tipo del registro dei nomi delle autorità emittenti viene specificato mediante `type` l'attributo.</span><span class="sxs-lookup"><span data-stu-id="af931-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="af931-134">L' `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="af931-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="af931-135">Si fornisce la logica che elabora questi elementi figlio eseguendo l'override del <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="af931-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="af931-136">WIF fornisce un singolo tipo di registro dei nomi delle autorità emittenti, ovvero la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="af931-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="af931-137">Questa classe usa un set di certificati Autorità di certificazione attendibili specificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="af931-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="af931-138">Richiede un elemento di configurazione figlio, `<trustedIssuers>`, in cui è configurata la raccolta di certificati dell'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="af931-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="af931-139">I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti o rimossi dalla raccolta `<add>`tramite gli elementi, `<remove>` `<clear>`o.</span><span class="sxs-lookup"><span data-stu-id="af931-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="af931-140">L' `<issuerNameRegistry>` elemento è rappresentato <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="af931-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af931-141">Specificare l' `<issuerNameRegistry>` elemento come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="af931-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="af931-142">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="af931-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af931-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="af931-143">Example</span></span>  
 <span data-ttu-id="af931-144">Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="af931-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af931-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af931-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
