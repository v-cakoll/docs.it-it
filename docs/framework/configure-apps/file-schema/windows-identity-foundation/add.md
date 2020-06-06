---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73973808"
---
# \<add>
<span data-ttu-id="25fb2-101">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="25fb2-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="25fb2-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25fb2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25fb2-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="25fb2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="25fb2-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="25fb2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25fb2-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="25fb2-105">Attributes</span></span>  
  
|<span data-ttu-id="25fb2-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="25fb2-106">Attribute</span></span>|<span data-ttu-id="25fb2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25fb2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25fb2-108">type</span><span class="sxs-lookup"><span data-stu-id="25fb2-108">type</span></span>|<span data-ttu-id="25fb2-109">Nome del tipo CLR del gestore di token da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="25fb2-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="25fb2-110">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="25fb2-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25fb2-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="25fb2-111">Child Elements</span></span>  
  
|<span data-ttu-id="25fb2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="25fb2-112">Element</span></span>|<span data-ttu-id="25fb2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25fb2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="25fb2-114">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> classe, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="25fb2-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="25fb2-115">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="25fb2-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="25fb2-116">Fornisce la configurazione per la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="25fb2-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="25fb2-117">Fornisce la configurazione facoltativa per la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="25fb2-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25fb2-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="25fb2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="25fb2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="25fb2-119">Element</span></span>|<span data-ttu-id="25fb2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25fb2-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="25fb2-121">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="25fb2-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25fb2-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="25fb2-122">Remarks</span></span>  
 <span data-ttu-id="25fb2-123">L' `<add>` elemento può assumere un singolo elemento figlio che specifica la configurazione per il gestore del token.</span><span class="sxs-lookup"><span data-stu-id="25fb2-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="25fb2-124">Questo dipende dal fatto che la classe del gestore a cui viene fatto riferimento tramite l' `type` attributo dell' `<add>` elemento fornisca il supporto per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="25fb2-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="25fb2-125">Le classi del gestore di token che forniscono questa funzionalità devono esporre un costruttore che accetta un <xref:System.Xml.XmlElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="25fb2-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="25fb2-126">Diverse classi del gestore del token di sicurezza predefinite forniscono questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="25fb2-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="25fb2-127">Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="25fb2-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="25fb2-128">La raccolta di gestori di token può contenere solo un singolo gestore di qualsiasi tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="25fb2-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="25fb2-129">Ciò significa, ad esempio, che se si desidera aggiungere un gestore derivato dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario innanzitutto rimuovere <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , che è presente per impostazione predefinita, dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="25fb2-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="25fb2-130">È possibile utilizzare l' [\<remove>](remove.md) elemento per rimuovere un singolo gestore dalla raccolta oppure utilizzare l' [\<clear>](clear.md) elemento per rimuovere tutti i gestori dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="25fb2-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="25fb2-131">Le impostazioni specificate in un gestore eseguono l'override di impostazioni equivalenti specificate nella raccolta di gestori di token nell' [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento e quelle specificate a livello di servizio nell' [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="25fb2-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25fb2-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="25fb2-132">Example</span></span>  
 <span data-ttu-id="25fb2-133">Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="25fb2-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="25fb2-134">Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="25fb2-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
