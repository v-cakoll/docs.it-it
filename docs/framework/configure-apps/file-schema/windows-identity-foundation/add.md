---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 932e8452542ace66824fba1262694c220ce88676
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252181"
---
# <a name="add"></a><span data-ttu-id="107a7-101">\<add></span><span class="sxs-lookup"><span data-stu-id="107a7-101">\<add></span></span>
<span data-ttu-id="107a7-102">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="107a7-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="107a7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="107a7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="107a7-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="107a7-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="107a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="107a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="107a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="107a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="107a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="107a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107a7-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="107a7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="107a7-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="107a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="107a7-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="107a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="107a7-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="107a7-111">Attributes</span></span>  
  
|<span data-ttu-id="107a7-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="107a7-112">Attribute</span></span>|<span data-ttu-id="107a7-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="107a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="107a7-114">type</span><span class="sxs-lookup"><span data-stu-id="107a7-114">type</span></span>|<span data-ttu-id="107a7-115">Nome del tipo CLR del gestore di token da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="107a7-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="107a7-116">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="107a7-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="107a7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="107a7-117">Child Elements</span></span>  
  
|<span data-ttu-id="107a7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="107a7-118">Element</span></span>|<span data-ttu-id="107a7-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107a7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="107a7-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="107a7-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="107a7-121">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="107a7-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="107a7-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="107a7-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="107a7-123">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="107a7-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="107a7-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="107a7-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="107a7-125">Fornisce la configurazione per <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="107a7-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="107a7-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="107a7-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="107a7-127">Fornisce la configurazione facoltativa <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> per la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="107a7-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="107a7-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="107a7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="107a7-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="107a7-129">Element</span></span>|<span data-ttu-id="107a7-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107a7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="107a7-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="107a7-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="107a7-132">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="107a7-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="107a7-133">Note</span><span class="sxs-lookup"><span data-stu-id="107a7-133">Remarks</span></span>  
 <span data-ttu-id="107a7-134">L' `<add>` elemento può assumere un singolo elemento figlio che specifica la configurazione per il gestore del token.</span><span class="sxs-lookup"><span data-stu-id="107a7-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="107a7-135">Questo dipende dal fatto che la classe del gestore a cui viene `type` fatto riferimento tramite `<add>` l'attributo dell'elemento fornisca il supporto per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="107a7-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="107a7-136">Le classi del gestore di token che forniscono questa funzionalità devono esporre un costruttore <xref:System.Xml.XmlElement> che accetta un oggetto.</span><span class="sxs-lookup"><span data-stu-id="107a7-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="107a7-137">Diverse classi del gestore del token di sicurezza predefinite forniscono questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="107a7-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="107a7-138">Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, e<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="107a7-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="107a7-139">La raccolta di gestori di token può contenere solo un singolo gestore di qualsiasi tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="107a7-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="107a7-140">Ciò significa, ad esempio, che se si desidera aggiungere un gestore derivato dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario innanzitutto <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>rimuovere, che è presente per impostazione predefinita, dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="107a7-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="107a7-141">È possibile utilizzare l' [ \<elemento remove >](remove.md) per rimuovere un singolo gestore dalla raccolta oppure utilizzare l' [ \<elemento clear >](clear.md) per rimuovere tutti i gestori dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="107a7-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="107a7-142">Le impostazioni specificate in un gestore eseguono l'override delle impostazioni equivalenti specificate nella raccolta di gestori di token nell' [ \<elemento securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md) e quelle specificate a livello di servizio nel [ \< identityConfiguration >](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="107a7-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="107a7-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="107a7-143">Example</span></span>  
 <span data-ttu-id="107a7-144">Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="107a7-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="107a7-145">Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="107a7-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
