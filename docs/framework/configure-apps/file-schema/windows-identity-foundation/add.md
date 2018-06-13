---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6ee6403fcfe741d3e38bf44eddb1cf52cf856ec8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757853"
---
# <a name="ltaddgt"></a><span data-ttu-id="74720-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="74720-102">&lt;add&gt;</span></span>
<span data-ttu-id="74720-103">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="74720-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="74720-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="74720-104">\<system.identityModel></span></span>  
<span data-ttu-id="74720-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="74720-105">\<identityConfiguration></span></span>  
<span data-ttu-id="74720-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="74720-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="74720-107">\<add></span><span class="sxs-lookup"><span data-stu-id="74720-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74720-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74720-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74720-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="74720-109">Attributes and Elements</span></span>  
 <span data-ttu-id="74720-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="74720-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74720-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="74720-111">Attributes</span></span>  
  
|<span data-ttu-id="74720-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="74720-112">Attribute</span></span>|<span data-ttu-id="74720-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74720-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74720-114">tipo</span><span class="sxs-lookup"><span data-stu-id="74720-114">type</span></span>|<span data-ttu-id="74720-115">Il nome del tipo CLR il gestore dei token da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="74720-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="74720-116">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="74720-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74720-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74720-117">Child Elements</span></span>  
  
|<span data-ttu-id="74720-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="74720-118">Element</span></span>|<span data-ttu-id="74720-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74720-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74720-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="74720-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="74720-121">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="74720-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="74720-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="74720-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="74720-123">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="74720-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="74720-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="74720-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="74720-125">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="74720-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="74720-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="74720-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="74720-127">Fornisce la configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="74720-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74720-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="74720-128">Parent Elements</span></span>  
  
|<span data-ttu-id="74720-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="74720-129">Element</span></span>|<span data-ttu-id="74720-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74720-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74720-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="74720-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="74720-132">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="74720-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74720-133">Note</span><span class="sxs-lookup"><span data-stu-id="74720-133">Remarks</span></span>  
 <span data-ttu-id="74720-134">Il `<add>` elemento può richiedere un singolo elemento figlio che specifica la configurazione per il gestore dei token.</span><span class="sxs-lookup"><span data-stu-id="74720-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="74720-135">Questo è dipendente se la classe del gestore viene fatto riferimento tramite il `type` attributo del `<add>` elemento offre il supporto per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74720-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="74720-136">Le classi del gestore di token che forniscono questa funzionalità devono esporre un costruttore che accetta un <xref:System.Xml.XmlElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="74720-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="74720-137">Molte delle classi di gestore dei token di sicurezza incorporati offre questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="74720-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="74720-138">Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="74720-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74720-139">Raccolta di gestori di token può contenere solo un singolo gestore di un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="74720-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="74720-140">Ciò significa, ad esempio, che se si desidera aggiungere un gestore che è derivato dal <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario rimuovere prima il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, che è presente per impostazione predefinita, dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="74720-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="74720-141">È possibile utilizzare il [ \<rimuovere >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento da rimuovere un singolo gestore dalla raccolta o utilizzare il [ \<deselezionare >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento da rimuovere tutti i gestori dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="74720-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="74720-142">Le impostazioni specificate in un gestore sostituiscono impostazioni equivalenti specificate nella raccolta di gestori di token nel [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento e quelli specificati a livello di servizio in il [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="74720-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74720-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="74720-143">Example</span></span>  
 <span data-ttu-id="74720-144">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="74720-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="74720-145">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="74720-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
