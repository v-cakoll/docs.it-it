---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152671"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="78578-101">\<IssuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="78578-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="78578-102">Registra il resolver di token dell'autorità di certificazione utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="78578-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="78578-103">Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="78578-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="78578-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78578-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78578-105">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="78578-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="78578-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="78578-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="78578-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="78578-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="78578-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="78578-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="78578-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="78578-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78578-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78578-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78578-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78578-111">Attributes and Elements</span></span>  
 <span data-ttu-id="78578-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78578-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78578-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="78578-113">Attributes</span></span>  
  
|<span data-ttu-id="78578-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="78578-114">Attribute</span></span>|<span data-ttu-id="78578-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78578-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78578-116">type</span><span class="sxs-lookup"><span data-stu-id="78578-116">type</span></span>|<span data-ttu-id="78578-117">Specifica il tipo di resolver del token dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="78578-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="78578-118">Deve essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> la classe o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> che deriva dalla classe.</span><span class="sxs-lookup"><span data-stu-id="78578-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="78578-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="78578-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78578-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78578-120">Child Elements</span></span>  
 <span data-ttu-id="78578-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="78578-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78578-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78578-122">Parent Elements</span></span>  
  
|<span data-ttu-id="78578-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="78578-123">Element</span></span>|<span data-ttu-id="78578-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78578-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78578-125">\<>securityTokenHandlerConfiguration</span><span class="sxs-lookup"><span data-stu-id="78578-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="78578-126">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="78578-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78578-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="78578-127">Remarks</span></span>  
 <span data-ttu-id="78578-128">Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="78578-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="78578-129">Viene utilizzato per recuperare il materiale crittografico utilizzato per controllare la firma.</span><span class="sxs-lookup"><span data-stu-id="78578-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="78578-130">È necessario `type` specificare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="78578-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="78578-131">Il tipo specificato <xref:System.IdentityModel.Tokens.IssuerTokenResolver> può essere o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> personalizzato che deriva dalla classe .</span><span class="sxs-lookup"><span data-stu-id="78578-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="78578-132">Alcuni gestori di token consentono di specificare le impostazioni del resolver del token dell'autorità di certificazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="78578-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="78578-133">Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="78578-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78578-134">Specificare `<issuerTokenResolver>` l'elemento come elemento figlio dell'elemento [ \<identityConfiguration>](identityconfiguration.md) è deprecato, ma è comunque supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="78578-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="78578-135">Le impostazioni `<securityTokenHandlerConfiguration>` dell'elemento `<identityConfiguration>` sostituiscono quelle dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="78578-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78578-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="78578-136">Example</span></span>  
 <span data-ttu-id="78578-137">Nel codice XML seguente viene illustrata la configurazione per un resolver <xref:System.IdentityModel.Tokens.IssuerTokenResolver>di token dell'autorità emittente basata su una classe personalizzata che deriva da .</span><span class="sxs-lookup"><span data-stu-id="78578-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="78578-138">Il resolver di token gestisce un dizionario di coppie audience-chiave inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="78578-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="78578-139">La classe esegue <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> l'override del metodo per elaborare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="78578-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="78578-140">L'override è illustrato nell'esempio seguente. tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="78578-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="78578-141">Per l'esempio completo, vedere l'esempio. `CustomToken`</span><span class="sxs-lookup"><span data-stu-id="78578-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="78578-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="78578-142">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="78578-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78578-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
