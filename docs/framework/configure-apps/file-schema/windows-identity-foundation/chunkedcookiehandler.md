---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941888"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="af831-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="af831-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="af831-102"><xref:System.IdentityModel.Services.ChunkedCookieHandler>Configura.</span><span class="sxs-lookup"><span data-stu-id="af831-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="af831-103">Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "default" o "Chunked".</span><span class="sxs-lookup"><span data-stu-id="af831-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="af831-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="af831-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="af831-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="af831-105">\<federationConfiguration></span></span>  
<span data-ttu-id="af831-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="af831-106">\<cookieHandler></span></span>  
<span data-ttu-id="af831-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="af831-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af831-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af831-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af831-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af831-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af831-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af831-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af831-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="af831-111">Attributes</span></span>  
  
|<span data-ttu-id="af831-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="af831-112">Attribute</span></span>|<span data-ttu-id="af831-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af831-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af831-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="af831-114">chunkSize</span></span>|<span data-ttu-id="af831-115">Dimensione massima, in caratteri, dei dati del cookie HTTP per un cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="af831-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="af831-116">È necessario prestare attenzione quando si modificano le dimensioni del blocco.</span><span class="sxs-lookup"><span data-stu-id="af831-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="af831-117">I Web browser hanno limiti diversi sulle dimensioni dei cookie e sul numero consentito per dominio.</span><span class="sxs-lookup"><span data-stu-id="af831-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="af831-118">Ad esempio, la specifica Netscape originale ha stabilito questi limiti: 300 cookie totali, 4096 byte per intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio.</span><span class="sxs-lookup"><span data-stu-id="af831-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="af831-119">Il valore predefinito è 2000.</span><span class="sxs-lookup"><span data-stu-id="af831-119">The default is 2000.</span></span> <span data-ttu-id="af831-120">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="af831-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af831-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af831-121">Child Elements</span></span>  
 <span data-ttu-id="af831-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="af831-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af831-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af831-123">Parent Elements</span></span>  
  
|<span data-ttu-id="af831-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="af831-124">Element</span></span>|<span data-ttu-id="af831-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af831-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af831-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="af831-126">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="af831-127">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> usato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="af831-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af831-128">Note</span><span class="sxs-lookup"><span data-stu-id="af831-128">Remarks</span></span>  
 <span data-ttu-id="af831-129">Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> oggetto impostando `mode` l'attributo dell' `<cookieHandler>` elemento su "default" o "Chunked", è possibile specificare la dimensione del blocco utilizzata dal gestore di cookie per leggere e scrivere cookie includendo `<chunkedCookieHandler>` un elemento figlio e impostazione del `chunkSize` relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="af831-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="af831-130">Se l' `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione del blocco predefinita di 2000 byte.</span><span class="sxs-lookup"><span data-stu-id="af831-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="af831-131">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="af831-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="af831-132">L' `<chunkedCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="af831-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af831-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="af831-133">Example</span></span>  
 <span data-ttu-id="af831-134">Nell'esempio seguente viene configurato un gestore di cookie Chunked che scrive cookie in blocchi di 3000 byte.</span><span class="sxs-lookup"><span data-stu-id="af831-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af831-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af831-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
