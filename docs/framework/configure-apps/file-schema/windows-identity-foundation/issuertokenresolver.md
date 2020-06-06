---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152671"
---
# \<issuerTokenResolver>
<span data-ttu-id="098bf-101">Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="098bf-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="098bf-102">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="098bf-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="098bf-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="098bf-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="098bf-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="098bf-104">Attributes and Elements</span></span>  
 <span data-ttu-id="098bf-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="098bf-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="098bf-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="098bf-106">Attributes</span></span>  
  
|<span data-ttu-id="098bf-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="098bf-107">Attribute</span></span>|<span data-ttu-id="098bf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="098bf-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="098bf-109">type</span><span class="sxs-lookup"><span data-stu-id="098bf-109">type</span></span>|<span data-ttu-id="098bf-110">Specifica il tipo del resolver dei token dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="098bf-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="098bf-111">Deve essere la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva dalla <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="098bf-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="098bf-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="098bf-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="098bf-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="098bf-113">Child Elements</span></span>  
 <span data-ttu-id="098bf-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="098bf-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="098bf-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="098bf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="098bf-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="098bf-116">Element</span></span>|<span data-ttu-id="098bf-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="098bf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="098bf-118">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="098bf-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="098bf-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="098bf-119">Remarks</span></span>  
 <span data-ttu-id="098bf-120">Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="098bf-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="098bf-121">Viene utilizzato per recuperare il materiale crittografico utilizzato per il controllo della firma.</span><span class="sxs-lookup"><span data-stu-id="098bf-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="098bf-122">È necessario specificare l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="098bf-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="098bf-123">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="098bf-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="098bf-124">Alcuni gestori di token consentono di specificare le impostazioni del resolver dei token dell'autorità emittente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="098bf-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="098bf-125">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="098bf-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="098bf-126">Specificare l' `<issuerTokenResolver>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="098bf-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="098bf-127">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="098bf-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="098bf-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="098bf-128">Example</span></span>  
 <span data-ttu-id="098bf-129">Nel codice XML seguente viene illustrata la configurazione per un resolver dei token dell'autorità emittente basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="098bf-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="098bf-130">Il resolver di token mantiene un dizionario di coppie di chiavi di audience inizializzate da un elemento di configurazione personalizzato ( `<AddAudienceKeyPair>` ) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="098bf-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="098bf-131">La classe esegue l'override del <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodo per elaborare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="098bf-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="098bf-132">L'override è illustrato nell'esempio seguente: Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="098bf-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="098bf-133">Per l'esempio completo, vedere l'esempio `CustomToken` .</span><span class="sxs-lookup"><span data-stu-id="098bf-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="098bf-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="098bf-134">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="098bf-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="098bf-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
