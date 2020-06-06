---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251959"
---
# \<issuerNameRegistry>
<span data-ttu-id="e764b-101">Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e764b-101">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="e764b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e764b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e764b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e764b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e764b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e764b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e764b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="e764b-105">Attributes</span></span>  
  
|<span data-ttu-id="e764b-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="e764b-106">Attribute</span></span>|<span data-ttu-id="e764b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e764b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e764b-108">type</span><span class="sxs-lookup"><span data-stu-id="e764b-108">type</span></span>|<span data-ttu-id="e764b-109">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="e764b-109">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="e764b-110">Per ulteriori informazioni su come specificare un oggetto personalizzato `type` , vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="e764b-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e764b-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e764b-111">Child Elements</span></span>  
  
|<span data-ttu-id="e764b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e764b-112">Element</span></span>|<span data-ttu-id="e764b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e764b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="e764b-114">Quando l' `type` attributo specifica il registro dei nomi delle autorità emittenti basato sulla configurazione (la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), [\<trustedIssuers>](trustedissuers.md) è necessario specificare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e764b-114">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="e764b-115">L' [\<trustedIssuers>](trustedissuers.md) elemento può assumere `<add>` `<clear>` elementi, o `<remove>` come elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="e764b-115">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e764b-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e764b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e764b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e764b-117">Element</span></span>|<span data-ttu-id="e764b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e764b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e764b-119">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e764b-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e764b-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="e764b-120">Remarks</span></span>  
 <span data-ttu-id="e764b-121">Tutti i token dell'autorità emittente vengono convalidati utilizzando un registro di sistema del nome dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="e764b-121">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="e764b-122">Si tratta di un oggetto che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="e764b-122">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="e764b-123">Il registro dei nomi delle autorità emittenti viene utilizzato per associare un nome mnemonico al materiale crittografico necessario per verificare le firme dei token prodotti dall'emittente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e764b-123">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="e764b-124">Il registro dei nomi delle autorità emittenti gestisce un elenco di autorità di certificazione ritenute attendibili dall'applicazione relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="e764b-124">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="e764b-125">Il tipo del registro dei nomi delle autorità emittenti viene specificato mediante l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="e764b-125">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="e764b-126">L' `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="e764b-126">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="e764b-127">Si fornisce la logica che elabora questi elementi figlio eseguendo l'override del <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e764b-127">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="e764b-128">WIF fornisce un singolo tipo di registro dei nomi delle autorità emittenti, ovvero la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="e764b-128">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="e764b-129">Questa classe usa un set di certificati Autorità di certificazione attendibili specificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="e764b-129">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="e764b-130">Richiede un elemento di configurazione figlio, `<trustedIssuers>` , in cui è configurata la raccolta di certificati dell'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="e764b-130">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="e764b-131">I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti o rimossi dalla raccolta tramite `<add>` `<clear>` `<remove>` gli elementi, o.</span><span class="sxs-lookup"><span data-stu-id="e764b-131">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="e764b-132">L' `<issuerNameRegistry>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.</span><span class="sxs-lookup"><span data-stu-id="e764b-132">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e764b-133">Specificare l' `<issuerNameRegistry>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e764b-133">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e764b-134">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e764b-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e764b-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="e764b-135">Example</span></span>  
 <span data-ttu-id="e764b-136">Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e764b-136">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e764b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e764b-137">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
