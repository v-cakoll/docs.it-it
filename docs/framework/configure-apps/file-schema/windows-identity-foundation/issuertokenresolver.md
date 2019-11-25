---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968516"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="e7283-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="e7283-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="e7283-102">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e7283-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e7283-103">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e7283-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="e7283-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7283-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7283-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e7283-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e7283-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IdentityConfiguration**](identityconfiguration.md) ></span><span class="sxs-lookup"><span data-stu-id="e7283-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e7283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**securityTokenHandlers**](securitytokenhandlers.md) ></span><span class="sxs-lookup"><span data-stu-id="e7283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e7283-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md) ></span><span class="sxs-lookup"><span data-stu-id="e7283-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="e7283-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="e7283-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7283-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7283-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7283-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e7283-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7283-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e7283-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7283-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7283-113">Attributes</span></span>  
  
|<span data-ttu-id="e7283-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7283-114">Attribute</span></span>|<span data-ttu-id="e7283-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7283-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7283-116">tipo</span><span class="sxs-lookup"><span data-stu-id="e7283-116">type</span></span>|<span data-ttu-id="e7283-117">Specifica il tipo del resolver dei token dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="e7283-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e7283-118">Deve essere la classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo che deriva dalla classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e7283-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e7283-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e7283-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7283-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7283-120">Child Elements</span></span>  
 <span data-ttu-id="e7283-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="e7283-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7283-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e7283-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e7283-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7283-123">Element</span></span>|<span data-ttu-id="e7283-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7283-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7283-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e7283-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e7283-126">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e7283-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7283-127">Note</span><span class="sxs-lookup"><span data-stu-id="e7283-127">Remarks</span></span>  
 <span data-ttu-id="e7283-128">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e7283-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e7283-129">Viene utilizzato per recuperare il materiale crittografico utilizzato per il controllo della firma.</span><span class="sxs-lookup"><span data-stu-id="e7283-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e7283-130">È necessario specificare l'attributo `type`.</span><span class="sxs-lookup"><span data-stu-id="e7283-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="e7283-131">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dalla classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e7283-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e7283-132">Alcuni gestori di token consentono di specificare le impostazioni del resolver dei token dell'autorità emittente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7283-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e7283-133">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e7283-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7283-134">La specifica dell'elemento `<issuerTokenResolver>` come elemento figlio dell'elemento [\<IdentityConfiguration](identityconfiguration.md) è stata deprecata, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e7283-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e7283-135">Le impostazioni sull'elemento `<securityTokenHandlerConfiguration>` eseguono l'override di quelle nell'elemento `<identityConfiguration>`.</span><span class="sxs-lookup"><span data-stu-id="e7283-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7283-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7283-136">Example</span></span>  
 <span data-ttu-id="e7283-137">Nel codice XML seguente viene illustrata la configurazione di un resolver dei token dell'autorità emittente basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e7283-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e7283-138">Il resolver di token mantiene un dizionario di coppie di chiavi di audience inizializzate da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="e7283-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e7283-139">La classe esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> per elaborare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="e7283-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e7283-140">L'override è illustrato nell'esempio seguente: Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="e7283-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e7283-141">Per l'esempio completo, vedere l'esempio `CustomToken`.</span><span class="sxs-lookup"><span data-stu-id="e7283-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e7283-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7283-142">Example</span></span>
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="e7283-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7283-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
