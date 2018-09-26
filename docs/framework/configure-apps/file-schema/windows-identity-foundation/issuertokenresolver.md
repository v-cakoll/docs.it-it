---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: eefd18c206b7f013c3a423df424c795583c0dde8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216331"
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="289b6-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="289b6-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="289b6-103">Registra il resolver dei token che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="289b6-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="289b6-104">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="289b6-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="289b6-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="289b6-105">\<system.identityModel></span></span>  
<span data-ttu-id="289b6-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="289b6-106">\<identityConfiguration></span></span>  
<span data-ttu-id="289b6-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="289b6-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="289b6-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="289b6-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="289b6-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="289b6-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289b6-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="289b6-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="289b6-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="289b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="289b6-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="289b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="289b6-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="289b6-113">Attributes</span></span>  
  
|<span data-ttu-id="289b6-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="289b6-114">Attribute</span></span>|<span data-ttu-id="289b6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="289b6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="289b6-116">tipo</span><span class="sxs-lookup"><span data-stu-id="289b6-116">type</span></span>|<span data-ttu-id="289b6-117">Specifica il tipo di resolver di token dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="289b6-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="289b6-118">Deve essere il <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="289b6-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="289b6-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="289b6-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="289b6-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="289b6-120">Child Elements</span></span>  
 <span data-ttu-id="289b6-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="289b6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="289b6-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="289b6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="289b6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="289b6-123">Element</span></span>|<span data-ttu-id="289b6-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="289b6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="289b6-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="289b6-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="289b6-126">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="289b6-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="289b6-127">Note</span><span class="sxs-lookup"><span data-stu-id="289b6-127">Remarks</span></span>  
 <span data-ttu-id="289b6-128">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="289b6-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="289b6-129">Utilizzato per recuperare il materiale di crittografia utilizzato per la verifica della firma.</span><span class="sxs-lookup"><span data-stu-id="289b6-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="289b6-130">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="289b6-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="289b6-131">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="289b6-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="289b6-132">Alcuni gestori di token consentono di specificare le impostazioni del resolver di token dell'autorità di certificazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="289b6-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="289b6-133">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="289b6-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="289b6-134">Specifica la `<issuerTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="289b6-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="289b6-135">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="289b6-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="289b6-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="289b6-136">Example</span></span>  
 <span data-ttu-id="289b6-137">Il codice XML seguente mostra la configurazione per un resolver di token dell'autorità di certificazione basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="289b6-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="289b6-138">Il resolver dei token gestisce un dizionario di coppie di chiave di gruppo di destinatari che viene inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="289b6-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="289b6-139">La classe esegue l'override di <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodo per l'elaborazione di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="289b6-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="289b6-140">La sostituzione è illustrata nell'esempio seguente; Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="289b6-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="289b6-141">Per un esempio completo, vedere il `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="289b6-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="289b6-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="289b6-142">Example</span></span>  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="289b6-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="289b6-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
