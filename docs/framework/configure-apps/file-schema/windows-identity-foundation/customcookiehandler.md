---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b974767aa86801bff234e200e1fce021bfc422c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="848c0-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="848c0-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="848c0-103">Imposta il tipo di gestore cookie personalizzati.</span><span class="sxs-lookup"><span data-stu-id="848c0-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="848c0-104">Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Personalizzato".</span><span class="sxs-lookup"><span data-stu-id="848c0-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="848c0-105">Il tipo personalizzato deve essere derivato dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="848c0-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="848c0-106">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="848c0-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="848c0-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="848c0-107">\<federationConfiguration></span></span>  
<span data-ttu-id="848c0-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="848c0-108">\<cookieHandler></span></span>  
<span data-ttu-id="848c0-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="848c0-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848c0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="848c0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="848c0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="848c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="848c0-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="848c0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="848c0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="848c0-113">Attributes</span></span>  
  
|<span data-ttu-id="848c0-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="848c0-114">Attribute</span></span>|<span data-ttu-id="848c0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="848c0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="848c0-116">tipo</span><span class="sxs-lookup"><span data-stu-id="848c0-116">type</span></span>|<span data-ttu-id="848c0-117">Specifica un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="848c0-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="848c0-118">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="848c0-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="848c0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="848c0-119">Child Elements</span></span>  
 <span data-ttu-id="848c0-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="848c0-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="848c0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="848c0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="848c0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="848c0-122">Element</span></span>|<span data-ttu-id="848c0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="848c0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="848c0-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="848c0-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="848c0-125">Configura il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> utilizzata per leggere e scrivere i cookie.</span><span class="sxs-lookup"><span data-stu-id="848c0-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="848c0-126">Note</span><span class="sxs-lookup"><span data-stu-id="848c0-126">Remarks</span></span>  
 <span data-ttu-id="848c0-127">Quando si specifica un gestore personalizzato cookie impostando il `mode` attributo del `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="848c0-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="848c0-128">Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="848c0-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="848c0-129">I gestori di cookie personalizzato devono derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="848c0-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="848c0-130">Il `<customCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.</span><span class="sxs-lookup"><span data-stu-id="848c0-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="848c0-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="848c0-131">Example</span></span>  
 <span data-ttu-id="848c0-132">Nell'esempio seguente consente di configurare il modulo SAM per utilizzare un gestore personalizzato di cookie di tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="848c0-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="848c0-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="848c0-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
