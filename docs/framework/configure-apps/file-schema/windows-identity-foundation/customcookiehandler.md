---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942787"
---
# <a name="customcookiehandler"></a><span data-ttu-id="cff9a-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="cff9a-101">\<customCookieHandler></span></span>
<span data-ttu-id="cff9a-102">Imposta il tipo di gestore di cookie personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cff9a-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="cff9a-103">Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "Custom".</span><span class="sxs-lookup"><span data-stu-id="cff9a-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="cff9a-104">Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="cff9a-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cff9a-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="cff9a-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="cff9a-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="cff9a-106">\<federationConfiguration></span></span>  
<span data-ttu-id="cff9a-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="cff9a-107">\<cookieHandler></span></span>  
<span data-ttu-id="cff9a-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="cff9a-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff9a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cff9a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cff9a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cff9a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cff9a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cff9a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cff9a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cff9a-112">Attributes</span></span>  
  
|<span data-ttu-id="cff9a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cff9a-113">Attribute</span></span>|<span data-ttu-id="cff9a-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="cff9a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cff9a-115">type</span><span class="sxs-lookup"><span data-stu-id="cff9a-115">type</span></span>|<span data-ttu-id="cff9a-116">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="cff9a-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="cff9a-117">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="cff9a-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cff9a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cff9a-118">Child Elements</span></span>  
 <span data-ttu-id="cff9a-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="cff9a-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cff9a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cff9a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cff9a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="cff9a-121">Element</span></span>|<span data-ttu-id="cff9a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cff9a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cff9a-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="cff9a-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="cff9a-124">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> utilizzato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="cff9a-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff9a-125">Note</span><span class="sxs-lookup"><span data-stu-id="cff9a-125">Remarks</span></span>  
 <span data-ttu-id="cff9a-126">Quando si specifica un gestore di cookie personalizzato impostando `mode` l'attributo `<cookieHandler>` dell'elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="cff9a-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="cff9a-127">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Chunked" o "default".</span><span class="sxs-lookup"><span data-stu-id="cff9a-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="cff9a-128">I <xref:System.IdentityModel.Services.CookieHandler> gestori di cookie personalizzati devono derivare dalla classe.</span><span class="sxs-lookup"><span data-stu-id="cff9a-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cff9a-129">L' `<customCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Configuration.CustomTypeElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="cff9a-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff9a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="cff9a-130">Example</span></span>  
 <span data-ttu-id="cff9a-131">Nell'esempio seguente viene configurato il SAM per l'utilizzo di un gestore di cookie `MyNamespace.MyCustomCookieHandler`personalizzato di tipo.</span><span class="sxs-lookup"><span data-stu-id="cff9a-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cff9a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cff9a-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
