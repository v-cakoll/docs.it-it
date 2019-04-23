---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 08082d2e6647f07f33df72ab79dac00c15a1cd1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200818"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="d77f8-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d77f8-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="d77f8-102">Registra il resolver dei token che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d77f8-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d77f8-103">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="d77f8-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="d77f8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d77f8-104">\<system.identityModel></span></span>  
<span data-ttu-id="d77f8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d77f8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d77f8-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d77f8-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d77f8-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d77f8-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d77f8-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d77f8-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77f8-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d77f8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d77f8-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d77f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d77f8-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d77f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d77f8-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d77f8-112">Attributes</span></span>  
  
|<span data-ttu-id="d77f8-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d77f8-113">Attribute</span></span>|<span data-ttu-id="d77f8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d77f8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d77f8-115">tipo</span><span class="sxs-lookup"><span data-stu-id="d77f8-115">type</span></span>|<span data-ttu-id="d77f8-116">Specifica il tipo di resolver di token dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d77f8-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="d77f8-117">Deve essere il <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="d77f8-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="d77f8-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d77f8-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d77f8-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d77f8-119">Child Elements</span></span>  
 <span data-ttu-id="d77f8-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="d77f8-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d77f8-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d77f8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d77f8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d77f8-122">Element</span></span>|<span data-ttu-id="d77f8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d77f8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d77f8-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d77f8-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d77f8-125">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d77f8-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d77f8-126">Note</span><span class="sxs-lookup"><span data-stu-id="d77f8-126">Remarks</span></span>  
 <span data-ttu-id="d77f8-127">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="d77f8-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="d77f8-128">Utilizzato per recuperare il materiale di crittografia utilizzato per la verifica della firma.</span><span class="sxs-lookup"><span data-stu-id="d77f8-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="d77f8-129">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="d77f8-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="d77f8-130">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="d77f8-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="d77f8-131">Alcuni gestori di token consentono di specificare le impostazioni del resolver di token dell'autorità di certificazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="d77f8-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="d77f8-132">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d77f8-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d77f8-133">Specifica la `<issuerTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d77f8-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d77f8-134">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d77f8-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d77f8-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="d77f8-135">Example</span></span>  
 <span data-ttu-id="d77f8-136">Il codice XML seguente mostra la configurazione per un resolver di token dell'autorità di certificazione basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="d77f8-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="d77f8-137">Il resolver dei token gestisce un dizionario di coppie di chiave di gruppo di destinatari che viene inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="d77f8-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="d77f8-138">La classe esegue l'override di <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodo per l'elaborazione di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d77f8-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="d77f8-139">La sostituzione è illustrata nell'esempio seguente; Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="d77f8-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="d77f8-140">Per un esempio completo, vedere il `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="d77f8-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="d77f8-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="d77f8-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d77f8-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d77f8-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
