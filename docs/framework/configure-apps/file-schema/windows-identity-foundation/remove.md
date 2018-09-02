---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 596cab4494ef3ba200fd0a046d7935f648fb7c4f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422188"
---
# <a name="ltremovegt"></a><span data-ttu-id="eece6-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="eece6-102">&lt;remove&gt;</span></span>
<span data-ttu-id="eece6-103">Rimuove il gestore di token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="eece6-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="eece6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="eece6-104">\<system.identityModel></span></span>  
<span data-ttu-id="eece6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="eece6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="eece6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="eece6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="eece6-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="eece6-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eece6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eece6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eece6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eece6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eece6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eece6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eece6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="eece6-111">Attributes</span></span>  
  
|<span data-ttu-id="eece6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="eece6-112">Attribute</span></span>|<span data-ttu-id="eece6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eece6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eece6-114">tipo</span><span class="sxs-lookup"><span data-stu-id="eece6-114">type</span></span>|<span data-ttu-id="eece6-115">Il nome del tipo CLR il gestore dei token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="eece6-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="eece6-116">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="eece6-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="eece6-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eece6-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eece6-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eece6-118">Child Elements</span></span>  
 <span data-ttu-id="eece6-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="eece6-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eece6-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eece6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="eece6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="eece6-121">Element</span></span>|<span data-ttu-id="eece6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eece6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eece6-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="eece6-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="eece6-124">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="eece6-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eece6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="eece6-125">Example</span></span>  
 <span data-ttu-id="eece6-126">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="eece6-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="eece6-127">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="eece6-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
