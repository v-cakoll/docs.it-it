---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 34643d10ef1ed2e87152e5013634e62859e0594e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791768"
---
# <a name="add"></a><span data-ttu-id="2930d-101">\<add></span><span class="sxs-lookup"><span data-stu-id="2930d-101">\<add></span></span>
<span data-ttu-id="2930d-102">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="2930d-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="2930d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2930d-103">\<system.identityModel></span></span>  
<span data-ttu-id="2930d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2930d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="2930d-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2930d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2930d-106">\<add></span><span class="sxs-lookup"><span data-stu-id="2930d-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2930d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2930d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2930d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2930d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2930d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2930d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2930d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2930d-110">Attributes</span></span>  
  
|<span data-ttu-id="2930d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="2930d-111">Attribute</span></span>|<span data-ttu-id="2930d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2930d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2930d-113">tipo</span><span class="sxs-lookup"><span data-stu-id="2930d-113">type</span></span>|<span data-ttu-id="2930d-114">Il nome del tipo CLR il gestore dei token da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2930d-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="2930d-115">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="2930d-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2930d-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2930d-116">Child Elements</span></span>  
  
|<span data-ttu-id="2930d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2930d-117">Element</span></span>|<span data-ttu-id="2930d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2930d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2930d-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="2930d-119">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="2930d-120">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="2930d-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="2930d-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="2930d-121">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="2930d-122">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="2930d-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="2930d-123">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="2930d-123">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="2930d-124">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="2930d-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="2930d-125">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="2930d-125">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="2930d-126">Fornisce una configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="2930d-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2930d-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2930d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2930d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="2930d-128">Element</span></span>|<span data-ttu-id="2930d-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2930d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2930d-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2930d-130">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="2930d-131">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2930d-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2930d-132">Note</span><span class="sxs-lookup"><span data-stu-id="2930d-132">Remarks</span></span>  
 <span data-ttu-id="2930d-133">Il `<add>` elemento può accettare un singolo elemento figlio che specifica la configurazione per il gestore dei token.</span><span class="sxs-lookup"><span data-stu-id="2930d-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="2930d-134">Questo dipende dal fatto che la classe del gestore fa riferimento tramite il `type` attributo del `<add>` elemento fornisce il supporto per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2930d-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="2930d-135">Le classi di gestori di token che forniscono questa funzionalità devono esporre un costruttore che accetta un <xref:System.Xml.XmlElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="2930d-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="2930d-136">Alcune delle classi di gestori di token di sicurezza predefinite offrono questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2930d-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="2930d-137">Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="2930d-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2930d-138">La raccolta di gestori di token può contenere solo un singolo gestore di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="2930d-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="2930d-139">Ciò significa, ad esempio, che se si desidera aggiungere un gestore di è derivato dal <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario innanzitutto rimuovere il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, che è presente per impostazione predefinita, dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="2930d-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="2930d-140">È possibile usare la [ \<rimuovere >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento da rimuovere un singolo gestore dalla raccolta o usare i [ \<deselezionare >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento da rimuovere tutti i gestori dall'insieme.</span><span class="sxs-lookup"><span data-stu-id="2930d-140">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="2930d-141">Le impostazioni specificate in un gestore di eseguire l'override equivalenti impostazioni specificate nella raccolta di gestori di token con la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento e quelli specificati a livello di servizio in il [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2930d-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2930d-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="2930d-142">Example</span></span>  
 <span data-ttu-id="2930d-143">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2930d-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="2930d-144">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="2930d-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
