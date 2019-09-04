---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252011"
---
# <a name="customcookiehandler"></a><span data-ttu-id="9e062-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="9e062-101">\<customCookieHandler></span></span>
<span data-ttu-id="9e062-102">Imposta il tipo di gestore di cookie personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9e062-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="9e062-103">Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "Custom".</span><span class="sxs-lookup"><span data-stu-id="9e062-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="9e062-104">Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="9e062-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="9e062-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e062-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e062-106">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="9e062-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="9e062-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9e062-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="9e062-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cookieHandler**](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="9e062-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="9e062-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customCookieHandler**</span><span class="sxs-lookup"><span data-stu-id="9e062-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e062-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e062-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e062-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e062-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9e062-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e062-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e062-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e062-113">Attributes</span></span>  
  
|<span data-ttu-id="9e062-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="9e062-114">Attribute</span></span>|<span data-ttu-id="9e062-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9e062-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e062-116">type</span><span class="sxs-lookup"><span data-stu-id="9e062-116">type</span></span>|<span data-ttu-id="9e062-117">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="9e062-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="9e062-118">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9e062-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e062-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e062-119">Child Elements</span></span>  
 <span data-ttu-id="9e062-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="9e062-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e062-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e062-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e062-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e062-122">Element</span></span>|<span data-ttu-id="9e062-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e062-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e062-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="9e062-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="9e062-125">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> utilizzato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="9e062-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e062-126">Note</span><span class="sxs-lookup"><span data-stu-id="9e062-126">Remarks</span></span>  
 <span data-ttu-id="9e062-127">Quando si specifica un gestore di cookie personalizzato impostando `mode` l'attributo `<cookieHandler>` dell'elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="9e062-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="9e062-128">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Chunked" o "default".</span><span class="sxs-lookup"><span data-stu-id="9e062-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="9e062-129">I <xref:System.IdentityModel.Services.CookieHandler> gestori di cookie personalizzati devono derivare dalla classe.</span><span class="sxs-lookup"><span data-stu-id="9e062-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="9e062-130">L' `<customCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Configuration.CustomTypeElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="9e062-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e062-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e062-131">Example</span></span>  
 <span data-ttu-id="9e062-132">Nell'esempio seguente viene configurato il SAM per l'utilizzo di un gestore di cookie `MyNamespace.MyCustomCookieHandler`personalizzato di tipo.</span><span class="sxs-lookup"><span data-stu-id="9e062-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e062-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e062-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
