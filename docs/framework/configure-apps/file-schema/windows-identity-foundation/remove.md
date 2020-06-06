---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251920"
---
# \<remove>
<span data-ttu-id="dbeaa-101">Rimuove il gestore del token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="dbeaa-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbeaa-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbeaa-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbeaa-103">Attributes and Elements</span></span>  
 <span data-ttu-id="dbeaa-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbeaa-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbeaa-105">Attributes</span></span>  
  
|<span data-ttu-id="dbeaa-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="dbeaa-106">Attribute</span></span>|<span data-ttu-id="dbeaa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbeaa-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbeaa-108">type</span><span class="sxs-lookup"><span data-stu-id="dbeaa-108">type</span></span>|<span data-ttu-id="dbeaa-109">Nome del tipo CLR del gestore di token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="dbeaa-110">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="dbeaa-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="dbeaa-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbeaa-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbeaa-112">Child Elements</span></span>  
 <span data-ttu-id="dbeaa-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="dbeaa-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbeaa-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbeaa-114">Parent Elements</span></span>  
  
|<span data-ttu-id="dbeaa-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbeaa-115">Element</span></span>|<span data-ttu-id="dbeaa-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbeaa-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="dbeaa-117">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dbeaa-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbeaa-118">Example</span></span>  
 <span data-ttu-id="dbeaa-119">Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="dbeaa-120">Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
