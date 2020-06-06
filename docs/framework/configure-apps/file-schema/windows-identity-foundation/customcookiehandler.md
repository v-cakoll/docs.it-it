---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252011"
---
# \<customCookieHandler>
<span data-ttu-id="8a840-101">Imposta il tipo di gestore di cookie personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8a840-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="8a840-102">Questo elemento può essere presente solo se l' `mode` attributo dell' `<cookieHandler>` elemento è "Custom".</span><span class="sxs-lookup"><span data-stu-id="8a840-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="8a840-103">Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="8a840-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="8a840-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a840-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a840-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8a840-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8a840-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8a840-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a840-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="8a840-107">Attributes</span></span>  
  
|<span data-ttu-id="8a840-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="8a840-108">Attribute</span></span>|<span data-ttu-id="8a840-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a840-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a840-110">type</span><span class="sxs-lookup"><span data-stu-id="8a840-110">type</span></span>|<span data-ttu-id="8a840-111">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="8a840-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="8a840-112">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="8a840-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a840-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8a840-113">Child Elements</span></span>  
 <span data-ttu-id="8a840-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="8a840-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a840-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8a840-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8a840-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a840-116">Element</span></span>|<span data-ttu-id="8a840-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a840-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="8a840-118">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> utilizzato da per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="8a840-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a840-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="8a840-119">Remarks</span></span>  
 <span data-ttu-id="8a840-120">Quando si specifica un gestore di cookie personalizzato impostando l' `mode` attributo dell' `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie.</span><span class="sxs-lookup"><span data-stu-id="8a840-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="8a840-121">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Chunked" o "default".</span><span class="sxs-lookup"><span data-stu-id="8a840-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="8a840-122">I gestori di cookie personalizzati devono derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="8a840-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="8a840-123">L' `<customCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.</span><span class="sxs-lookup"><span data-stu-id="8a840-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a840-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a840-124">Example</span></span>  
 <span data-ttu-id="8a840-125">Nell'esempio seguente viene configurato il SAM per l'utilizzo di un gestore di cookie personalizzato di tipo `MyNamespace.MyCustomCookieHandler` .</span><span class="sxs-lookup"><span data-stu-id="8a840-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a840-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a840-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
