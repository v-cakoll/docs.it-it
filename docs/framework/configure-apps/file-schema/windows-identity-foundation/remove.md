---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: a54957458311e2d5941d1aa1c2486a2f66994d9b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288132"
---
# <a name="remove"></a><span data-ttu-id="dd814-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="dd814-101">\<remove></span></span>
<span data-ttu-id="dd814-102">Rimuove il gestore di token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dd814-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="dd814-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dd814-103">\<system.identityModel></span></span>  
<span data-ttu-id="dd814-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dd814-104">\<identityConfiguration></span></span>  
<span data-ttu-id="dd814-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dd814-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="dd814-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="dd814-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd814-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd814-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd814-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd814-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd814-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd814-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd814-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd814-110">Attributes</span></span>  
  
|<span data-ttu-id="dd814-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd814-111">Attribute</span></span>|<span data-ttu-id="dd814-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd814-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd814-113">tipo</span><span class="sxs-lookup"><span data-stu-id="dd814-113">type</span></span>|<span data-ttu-id="dd814-114">Il nome del tipo CLR il gestore dei token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="dd814-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="dd814-115">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="dd814-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="dd814-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd814-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd814-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd814-117">Child Elements</span></span>  
 <span data-ttu-id="dd814-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="dd814-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd814-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd814-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dd814-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd814-120">Element</span></span>|<span data-ttu-id="dd814-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd814-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd814-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dd814-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="dd814-123">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dd814-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd814-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd814-124">Example</span></span>  
 <span data-ttu-id="dd814-125">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="dd814-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="dd814-126">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="dd814-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
