---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ddbf1b822550876d849f830d80cff9a74311ba9c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43489864"
---
# <a name="ltaddgt"></a><span data-ttu-id="d218d-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="d218d-102">&lt;add&gt;</span></span>
<span data-ttu-id="d218d-103">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="d218d-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="d218d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d218d-104">\<system.identityModel></span></span>  
<span data-ttu-id="d218d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d218d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d218d-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d218d-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d218d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d218d-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d218d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d218d-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d218d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d218d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d218d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d218d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d218d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d218d-111">Attributes</span></span>  
  
|<span data-ttu-id="d218d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d218d-112">Attribute</span></span>|<span data-ttu-id="d218d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d218d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d218d-114">tipo</span><span class="sxs-lookup"><span data-stu-id="d218d-114">type</span></span>|<span data-ttu-id="d218d-115">Il nome del tipo CLR il gestore dei token da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="d218d-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="d218d-116">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="d218d-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d218d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d218d-117">Child Elements</span></span>  
  
|<span data-ttu-id="d218d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d218d-118">Element</span></span>|<span data-ttu-id="d218d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d218d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d218d-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d218d-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="d218d-121">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="d218d-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="d218d-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d218d-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="d218d-123">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d218d-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="d218d-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="d218d-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="d218d-125">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d218d-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="d218d-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="d218d-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="d218d-127">Fornisce una configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d218d-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d218d-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d218d-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d218d-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="d218d-129">Element</span></span>|<span data-ttu-id="d218d-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d218d-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d218d-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d218d-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="d218d-132">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d218d-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d218d-133">Note</span><span class="sxs-lookup"><span data-stu-id="d218d-133">Remarks</span></span>  
 <span data-ttu-id="d218d-134">Il `<add>` elemento può accettare un singolo elemento figlio che specifica la configurazione per il gestore dei token.</span><span class="sxs-lookup"><span data-stu-id="d218d-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="d218d-135">Questo dipende dal fatto che la classe del gestore fa riferimento tramite il `type` attributo del `<add>` elemento fornisce il supporto per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d218d-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="d218d-136">Le classi di gestori di token che forniscono questa funzionalità devono esporre un costruttore che accetta un <xref:System.Xml.XmlElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d218d-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="d218d-137">Alcune delle classi di gestori di token di sicurezza predefinite offrono questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d218d-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="d218d-138">Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="d218d-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d218d-139">La raccolta di gestori di token può contenere solo un singolo gestore di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="d218d-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="d218d-140">Ciò significa, ad esempio, che se si desidera aggiungere un gestore di è derivato dal <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario innanzitutto rimuovere il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, che è presente per impostazione predefinita, dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="d218d-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="d218d-141">È possibile usare la [ \<rimuovere >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento da rimuovere un singolo gestore dalla raccolta o usare i [ \<deselezionare >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento da rimuovere tutti i gestori dall'insieme.</span><span class="sxs-lookup"><span data-stu-id="d218d-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="d218d-142">Le impostazioni specificate in un gestore di eseguire l'override equivalenti impostazioni specificate nella raccolta di gestori di token con la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento e quelli specificati a livello di servizio in il [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d218d-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d218d-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="d218d-143">Example</span></span>  
 <span data-ttu-id="d218d-144">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d218d-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="d218d-145">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="d218d-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
