---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942576"
---
# <a name="remove"></a><span data-ttu-id="66661-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="66661-101">\<remove></span></span>
<span data-ttu-id="66661-102">Rimuove il gestore del token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="66661-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="66661-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="66661-103">\<system.identityModel></span></span>  
<span data-ttu-id="66661-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="66661-104">\<identityConfiguration></span></span>  
<span data-ttu-id="66661-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="66661-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="66661-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="66661-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66661-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66661-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66661-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66661-108">Attributes and Elements</span></span>  
 <span data-ttu-id="66661-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66661-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66661-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="66661-110">Attributes</span></span>  
  
|<span data-ttu-id="66661-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="66661-111">Attribute</span></span>|<span data-ttu-id="66661-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="66661-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66661-113">type</span><span class="sxs-lookup"><span data-stu-id="66661-113">type</span></span>|<span data-ttu-id="66661-114">Nome del tipo CLR del gestore di token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="66661-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="66661-115">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="66661-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="66661-116">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="66661-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66661-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66661-117">Child Elements</span></span>  
 <span data-ttu-id="66661-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="66661-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66661-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66661-119">Parent Elements</span></span>  
  
|<span data-ttu-id="66661-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="66661-120">Element</span></span>|<span data-ttu-id="66661-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="66661-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66661-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="66661-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="66661-123">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="66661-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66661-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="66661-124">Example</span></span>  
 <span data-ttu-id="66661-125">Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="66661-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="66661-126">Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="66661-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
