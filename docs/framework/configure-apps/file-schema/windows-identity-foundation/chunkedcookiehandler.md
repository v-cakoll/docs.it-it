---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="81b21-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="81b21-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="81b21-103">Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="81b21-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="81b21-104">Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".</span><span class="sxs-lookup"><span data-stu-id="81b21-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="81b21-105">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="81b21-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="81b21-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="81b21-106">\<federationConfiguration></span></span>  
<span data-ttu-id="81b21-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="81b21-107">\<cookieHandler></span></span>  
<span data-ttu-id="81b21-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="81b21-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b21-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81b21-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81b21-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="81b21-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81b21-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="81b21-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81b21-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="81b21-112">Attributes</span></span>  
  
|<span data-ttu-id="81b21-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="81b21-113">Attribute</span></span>|<span data-ttu-id="81b21-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81b21-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81b21-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="81b21-115">chunkSize</span></span>|<span data-ttu-id="81b21-116">Dimensione massima in caratteri, di dati dei cookie HTTP per di un cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="81b21-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="81b21-117">È necessario prestare attenzione quando si modifica la dimensione del blocco.</span><span class="sxs-lookup"><span data-stu-id="81b21-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="81b21-118">Browser Web hanno limiti diversi sulle dimensioni dei cookie e il numero consentito per ogni dominio.</span><span class="sxs-lookup"><span data-stu-id="81b21-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="81b21-119">Ad esempio, la specifica Netscape originale stipulata questi limiti: 300 cookie totali, pari a 4.096 byte per ogni intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio.</span><span class="sxs-lookup"><span data-stu-id="81b21-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="81b21-120">Il valore predefinito è 2000.</span><span class="sxs-lookup"><span data-stu-id="81b21-120">The default is 2000.</span></span> <span data-ttu-id="81b21-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="81b21-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81b21-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81b21-122">Child Elements</span></span>  
 <span data-ttu-id="81b21-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="81b21-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81b21-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="81b21-124">Parent Elements</span></span>  
  
|<span data-ttu-id="81b21-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="81b21-125">Element</span></span>|<span data-ttu-id="81b21-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81b21-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81b21-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="81b21-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="81b21-128">Configura il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) viene utilizzato per leggere e scrivere i cookie.</span><span class="sxs-lookup"><span data-stu-id="81b21-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81b21-129">Note</span><span class="sxs-lookup"><span data-stu-id="81b21-129">Remarks</span></span>  
 <span data-ttu-id="81b21-130">Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> impostando il `mode` attributo del `<cookieHandler>` elemento da "Default" o "Chunked", è possibile specificare le dimensioni del blocco utilizzata dal gestore di cookie per leggere e scrivere i cookie includendo un `<chunkedCookieHandler>` elemento figlio e l'impostazione relativa `chunkSize` attributo.</span><span class="sxs-lookup"><span data-stu-id="81b21-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="81b21-131">Se il `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione di blocco predefinito di 2000 byte.</span><span class="sxs-lookup"><span data-stu-id="81b21-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="81b21-132">Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="81b21-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="81b21-133">Il `<chunkedCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.</span><span class="sxs-lookup"><span data-stu-id="81b21-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81b21-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="81b21-134">Example</span></span>  
 <span data-ttu-id="81b21-135">Nell'esempio seguente consente di configurare un gestore di cookie in blocchi che scrive i cookie in blocchi di 3000 byte.</span><span class="sxs-lookup"><span data-stu-id="81b21-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81b21-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b21-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
