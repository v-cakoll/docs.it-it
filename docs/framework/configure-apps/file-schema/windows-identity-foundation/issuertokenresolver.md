---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942634"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="b24a6-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b24a6-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="b24a6-102">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b24a6-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b24a6-103">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b24a6-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b24a6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b24a6-104">\<system.identityModel></span></span>  
<span data-ttu-id="b24a6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b24a6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b24a6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b24a6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b24a6-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b24a6-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b24a6-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b24a6-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b24a6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b24a6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b24a6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b24a6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b24a6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b24a6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b24a6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b24a6-112">Attributes</span></span>  
  
|<span data-ttu-id="b24a6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b24a6-113">Attribute</span></span>|<span data-ttu-id="b24a6-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b24a6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b24a6-115">type</span><span class="sxs-lookup"><span data-stu-id="b24a6-115">type</span></span>|<span data-ttu-id="b24a6-116">Specifica il tipo del resolver dei token dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="b24a6-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b24a6-117">Deve essere la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva <xref:System.IdentityModel.Tokens.IssuerTokenResolver> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b24a6-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b24a6-118">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="b24a6-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b24a6-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b24a6-119">Child Elements</span></span>  
 <span data-ttu-id="b24a6-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b24a6-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b24a6-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b24a6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b24a6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b24a6-122">Element</span></span>|<span data-ttu-id="b24a6-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b24a6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b24a6-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b24a6-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b24a6-125">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b24a6-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b24a6-126">Note</span><span class="sxs-lookup"><span data-stu-id="b24a6-126">Remarks</span></span>  
 <span data-ttu-id="b24a6-127">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b24a6-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b24a6-128">Viene utilizzato per recuperare il materiale crittografico utilizzato per il controllo della firma.</span><span class="sxs-lookup"><span data-stu-id="b24a6-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b24a6-129">È necessario specificare l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="b24a6-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="b24a6-130">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva <xref:System.IdentityModel.Tokens.IssuerTokenResolver> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b24a6-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b24a6-131">Alcuni gestori di token consentono di specificare le impostazioni del resolver dei token dell'autorità emittente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="b24a6-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b24a6-132">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b24a6-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b24a6-133">Specificare l' `<issuerTokenResolver>` elemento come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b24a6-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b24a6-134">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b24a6-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b24a6-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="b24a6-135">Example</span></span>  
 <span data-ttu-id="b24a6-136">Nel codice XML seguente viene illustrata la configurazione per un resolver dei token dell'autorità emittente basato su una classe personalizzata <xref:System.IdentityModel.Tokens.IssuerTokenResolver>che deriva da.</span><span class="sxs-lookup"><span data-stu-id="b24a6-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b24a6-137">Il resolver di token mantiene un dizionario di coppie di chiavi di audience inizializzate da un elemento di configurazione`<AddAudienceKeyPair>`personalizzato () definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="b24a6-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b24a6-138">La classe esegue l' <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> override del metodo per elaborare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="b24a6-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b24a6-139">L'override è illustrato nell'esempio seguente: Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="b24a6-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b24a6-140">Per l'esempio completo, vedere l' `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="b24a6-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b24a6-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="b24a6-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b24a6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b24a6-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
