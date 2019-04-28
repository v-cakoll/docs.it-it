---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 08082d2e6647f07f33df72ab79dac00c15a1cd1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791612"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="fcc6c-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="fcc6c-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="fcc6c-102">Registra il resolver dei token che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fcc6c-103">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="fcc6c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fcc6c-104">\<system.identityModel></span></span>  
<span data-ttu-id="fcc6c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fcc6c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="fcc6c-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="fcc6c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fcc6c-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="fcc6c-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="fcc6c-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="fcc6c-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc6c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcc6c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcc6c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fcc6c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fcc6c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcc6c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fcc6c-112">Attributes</span></span>  
  
|<span data-ttu-id="fcc6c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fcc6c-113">Attribute</span></span>|<span data-ttu-id="fcc6c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcc6c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcc6c-115">tipo</span><span class="sxs-lookup"><span data-stu-id="fcc6c-115">type</span></span>|<span data-ttu-id="fcc6c-116">Specifica il tipo di resolver di token dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="fcc6c-117">Deve essere il <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="fcc6c-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcc6c-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fcc6c-119">Child Elements</span></span>  
 <span data-ttu-id="fcc6c-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="fcc6c-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fcc6c-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fcc6c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fcc6c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcc6c-122">Element</span></span>|<span data-ttu-id="fcc6c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcc6c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcc6c-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="fcc6c-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="fcc6c-125">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc6c-126">Note</span><span class="sxs-lookup"><span data-stu-id="fcc6c-126">Remarks</span></span>  
 <span data-ttu-id="fcc6c-127">Il resolver dei token viene usato per risolvere il token di firma nel token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="fcc6c-128">Utilizzato per recuperare il materiale di crittografia utilizzato per la verifica della firma.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="fcc6c-129">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="fcc6c-130">Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="fcc6c-131">Alcuni gestori di token consentono di specificare le impostazioni del resolver di token dell'autorità di certificazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="fcc6c-132">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcc6c-133">Specifica la `<issuerTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="fcc6c-134">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc6c-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcc6c-135">Example</span></span>  
 <span data-ttu-id="fcc6c-136">Il codice XML seguente mostra la configurazione per un resolver di token dell'autorità di certificazione basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="fcc6c-137">Il resolver dei token gestisce un dizionario di coppie di chiave di gruppo di destinatari che viene inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="fcc6c-138">La classe esegue l'override di <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodo per l'elaborazione di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="fcc6c-139">La sostituzione è illustrata nell'esempio seguente; Tuttavia, i metodi che chiama non vengono visualizzati per brevità.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="fcc6c-140">Per un esempio completo, vedere il `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="fcc6c-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="fcc6c-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcc6c-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fcc6c-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc6c-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
