---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 752b1188fccb6f09cdcab6a50653abf26e8e2a53
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288184"
---
# <a name="customcookiehandler"></a><span data-ttu-id="9933d-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="9933d-101">\<customCookieHandler></span></span>
<span data-ttu-id="9933d-102">Imposta il tipo di gestore di cookie personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9933d-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="9933d-103">Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Custom".</span><span class="sxs-lookup"><span data-stu-id="9933d-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="9933d-104">Il tipo personalizzato deve derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="9933d-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="9933d-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="9933d-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="9933d-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="9933d-106">\<federationConfiguration></span></span>  
<span data-ttu-id="9933d-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="9933d-107">\<cookieHandler></span></span>  
<span data-ttu-id="9933d-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="9933d-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9933d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9933d-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9933d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9933d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9933d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9933d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9933d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9933d-112">Attributes</span></span>  
  
|<span data-ttu-id="9933d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9933d-113">Attribute</span></span>|<span data-ttu-id="9933d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9933d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9933d-115">tipo</span><span class="sxs-lookup"><span data-stu-id="9933d-115">type</span></span>|<span data-ttu-id="9933d-116">Specifica un tipo personalizzato che deriva dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="9933d-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="9933d-117">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9933d-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9933d-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9933d-118">Child Elements</span></span>  
 <span data-ttu-id="9933d-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="9933d-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9933d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9933d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9933d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9933d-121">Element</span></span>|<span data-ttu-id="9933d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9933d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9933d-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="9933d-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="9933d-124">Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> viene utilizzato per leggere e scrivere i cookie.</span><span class="sxs-lookup"><span data-stu-id="9933d-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9933d-125">Note</span><span class="sxs-lookup"><span data-stu-id="9933d-125">Remarks</span></span>  
 <span data-ttu-id="9933d-126">Quando si specifica un gestore di cookie personalizzato impostando il `mode` attributo del `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato, includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="9933d-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="9933d-127">Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="9933d-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="9933d-128">I gestori di cookie personalizzato devono derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="9933d-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="9933d-129">Il `<customCookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.</span><span class="sxs-lookup"><span data-stu-id="9933d-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9933d-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="9933d-130">Example</span></span>  
 <span data-ttu-id="9933d-131">L'esempio seguente configura il modulo SAM per utilizzare un gestore di cookie personalizzato di tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="9933d-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9933d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9933d-132">See also</span></span>
- <xref:System.IdentityModel.Services.CookieHandler>
