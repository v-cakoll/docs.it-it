---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758417"
---
# <a name="remove"></a><span data-ttu-id="e8bef-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="e8bef-101">\<remove></span></span>
<span data-ttu-id="e8bef-102">Rimuove il gestore di token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e8bef-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="e8bef-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e8bef-103">\<system.identityModel></span></span>  
<span data-ttu-id="e8bef-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e8bef-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e8bef-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e8bef-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e8bef-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="e8bef-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8bef-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8bef-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8bef-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8bef-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8bef-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8bef-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8bef-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8bef-110">Attributes</span></span>  
  
|<span data-ttu-id="e8bef-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8bef-111">Attribute</span></span>|<span data-ttu-id="e8bef-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8bef-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8bef-113">tipo</span><span class="sxs-lookup"><span data-stu-id="e8bef-113">type</span></span>|<span data-ttu-id="e8bef-114">Il nome del tipo CLR il gestore dei token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e8bef-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="e8bef-115">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="e8bef-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="e8bef-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e8bef-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8bef-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8bef-117">Child Elements</span></span>  
 <span data-ttu-id="e8bef-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="e8bef-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8bef-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8bef-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e8bef-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8bef-120">Element</span></span>|<span data-ttu-id="e8bef-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8bef-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8bef-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e8bef-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="e8bef-123">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e8bef-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8bef-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8bef-124">Example</span></span>  
 <span data-ttu-id="e8bef-125">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e8bef-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="e8bef-126">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="e8bef-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
