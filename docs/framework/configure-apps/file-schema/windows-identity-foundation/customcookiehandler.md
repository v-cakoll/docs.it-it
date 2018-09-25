---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081591"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="7510e-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="7510e-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="7510e-103">Imposta il tipo di gestore di cookie personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7510e-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="7510e-104">Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Custom".</span><span class="sxs-lookup"><span data-stu-id="7510e-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="7510e-105">Il tipo personalizzato deve derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="7510e-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="7510e-106">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="7510e-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="7510e-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7510e-107">\<federationConfiguration></span></span>  
<span data-ttu-id="7510e-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="7510e-108">\<cookieHandler></span></span>  
<span data-ttu-id="7510e-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="7510e-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7510e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7510e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7510e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7510e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7510e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7510e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7510e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7510e-113">Attributes</span></span>  
  
|<span data-ttu-id="7510e-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7510e-114">Attribute</span></span>|<span data-ttu-id="7510e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7510e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7510e-116">tipo</span><span class="sxs-lookup"><span data-stu-id="7510e-116">type</span></span>|<span data-ttu-id="7510e-117">Specifica un tipo personalizzato che deriva dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="7510e-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="7510e-118">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="7510e-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7510e-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7510e-119">Child Elements</span></span>  
 <span data-ttu-id="7510e-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="7510e-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7510e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7510e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7510e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7510e-122">Element</span></span>|<span data-ttu-id="7510e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7510e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7510e-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="7510e-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="7510e-125">Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> viene utilizzato per leggere e scrivere i cookie.</span><span class="sxs-lookup"><span data-stu-id="7510e-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7510e-126">Note</span><span class="sxs-lookup"><span data-stu-id="7510e-126">Remarks</span></span>  
 <span data-ttu-id="7510e-127">Quando si specifica un gestore di cookie personalizzato impostando il `mode` attributo del `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato, includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="7510e-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="7510e-128">Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="7510e-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="7510e-129">I gestori di cookie personalizzato devono derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="7510e-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="7510e-130">Il `<customCookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.</span><span class="sxs-lookup"><span data-stu-id="7510e-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7510e-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="7510e-131">Example</span></span>  
 <span data-ttu-id="7510e-132">L'esempio seguente configura il modulo SAM per utilizzare un gestore di cookie personalizzato di tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="7510e-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7510e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7510e-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
