---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252113"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="717f5-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="717f5-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="717f5-102"><xref:System.IdentityModel.Services.ChunkedCookieHandler>Configura.</span><span class="sxs-lookup"><span data-stu-id="717f5-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="717f5-103">Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "default" o "Chunked".</span><span class="sxs-lookup"><span data-stu-id="717f5-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="717f5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="717f5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="717f5-105">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="717f5-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="717f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="717f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="717f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cookieHandler**](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="717f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="717f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> chunkedCookieHandler**</span><span class="sxs-lookup"><span data-stu-id="717f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717f5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="717f5-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="717f5-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="717f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="717f5-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="717f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="717f5-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="717f5-112">Attributes</span></span>  
  
|<span data-ttu-id="717f5-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="717f5-113">Attribute</span></span>|<span data-ttu-id="717f5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="717f5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="717f5-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="717f5-115">chunkSize</span></span>|<span data-ttu-id="717f5-116">Dimensione massima, in caratteri, dei dati del cookie HTTP per un cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="717f5-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="717f5-117">È necessario prestare attenzione quando si modificano le dimensioni del blocco.</span><span class="sxs-lookup"><span data-stu-id="717f5-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="717f5-118">I Web browser hanno limiti diversi sulle dimensioni dei cookie e sul numero consentito per dominio.</span><span class="sxs-lookup"><span data-stu-id="717f5-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="717f5-119">Ad esempio, la specifica Netscape originale ha stabilito questi limiti: 300 cookie totali, 4096 byte per intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio.</span><span class="sxs-lookup"><span data-stu-id="717f5-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="717f5-120">Il valore predefinito è 2000.</span><span class="sxs-lookup"><span data-stu-id="717f5-120">The default is 2000.</span></span> <span data-ttu-id="717f5-121">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="717f5-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="717f5-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="717f5-122">Child Elements</span></span>  
 <span data-ttu-id="717f5-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="717f5-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="717f5-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="717f5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="717f5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="717f5-125">Element</span></span>|<span data-ttu-id="717f5-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="717f5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="717f5-127">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="717f5-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="717f5-128">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> usato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="717f5-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="717f5-129">Note</span><span class="sxs-lookup"><span data-stu-id="717f5-129">Remarks</span></span>  
 <span data-ttu-id="717f5-130">Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> oggetto impostando `mode` l'attributo dell' `<cookieHandler>` elemento su "default" o "Chunked", è possibile specificare la dimensione del blocco utilizzata dal gestore di cookie per leggere e scrivere cookie includendo `<chunkedCookieHandler>` un elemento figlio e impostazione del `chunkSize` relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="717f5-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="717f5-131">Se l' `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione del blocco predefinita di 2000 byte.</span><span class="sxs-lookup"><span data-stu-id="717f5-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="717f5-132">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="717f5-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="717f5-133">L' `<chunkedCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="717f5-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="717f5-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="717f5-134">Example</span></span>  
 <span data-ttu-id="717f5-135">Nell'esempio seguente viene configurato un gestore di cookie Chunked che scrive cookie in blocchi di 3000 byte.</span><span class="sxs-lookup"><span data-stu-id="717f5-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="717f5-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="717f5-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
