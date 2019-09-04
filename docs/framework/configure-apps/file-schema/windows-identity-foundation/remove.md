---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251920"
---
# <a name="remove"></a><span data-ttu-id="716bb-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="716bb-101">\<remove></span></span>
<span data-ttu-id="716bb-102">Rimuove il gestore del token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="716bb-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="716bb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="716bb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="716bb-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="716bb-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="716bb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="716bb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="716bb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="716bb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="716bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="716bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716bb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="716bb-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="716bb-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="716bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="716bb-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="716bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="716bb-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="716bb-111">Attributes</span></span>  
  
|<span data-ttu-id="716bb-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="716bb-112">Attribute</span></span>|<span data-ttu-id="716bb-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="716bb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="716bb-114">type</span><span class="sxs-lookup"><span data-stu-id="716bb-114">type</span></span>|<span data-ttu-id="716bb-115">Nome del tipo CLR del gestore di token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="716bb-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="716bb-116">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="716bb-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="716bb-117">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="716bb-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="716bb-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="716bb-118">Child Elements</span></span>  
 <span data-ttu-id="716bb-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="716bb-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="716bb-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="716bb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="716bb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="716bb-121">Element</span></span>|<span data-ttu-id="716bb-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="716bb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="716bb-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="716bb-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="716bb-124">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="716bb-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="716bb-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="716bb-125">Example</span></span>  
 <span data-ttu-id="716bb-126">Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="716bb-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="716bb-127">Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="716bb-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
