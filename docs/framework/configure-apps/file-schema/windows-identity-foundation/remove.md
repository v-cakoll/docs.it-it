---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793887"
---
# <a name="remove"></a><span data-ttu-id="f8ef1-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="f8ef1-101">\<remove></span></span>
<span data-ttu-id="f8ef1-102">Rimuove il gestore di token di sicurezza specificato dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="f8ef1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f8ef1-103">\<system.identityModel></span></span>  
<span data-ttu-id="f8ef1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f8ef1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f8ef1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f8ef1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f8ef1-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="f8ef1-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ef1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8ef1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8ef1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8ef1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f8ef1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8ef1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8ef1-110">Attributes</span></span>  
  
|<span data-ttu-id="f8ef1-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8ef1-111">Attribute</span></span>|<span data-ttu-id="f8ef1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8ef1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8ef1-113">tipo</span><span class="sxs-lookup"><span data-stu-id="f8ef1-113">type</span></span>|<span data-ttu-id="f8ef1-114">Il nome del tipo CLR il gestore dei token da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="f8ef1-115">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="f8ef1-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="f8ef1-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8ef1-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8ef1-117">Child Elements</span></span>  
 <span data-ttu-id="f8ef1-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="f8ef1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8ef1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8ef1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f8ef1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8ef1-120">Element</span></span>|<span data-ttu-id="f8ef1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8ef1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8ef1-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f8ef1-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="f8ef1-123">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8ef1-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8ef1-124">Example</span></span>  
 <span data-ttu-id="f8ef1-125">Il codice XML seguente viene illustrato come utilizzare il `<add>` e `<remove>` elementi per sostituire il gestore di token di sessione predefinito con un gestore di token di sessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="f8ef1-126">Il codice XML viene prelevato il `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="f8ef1-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
