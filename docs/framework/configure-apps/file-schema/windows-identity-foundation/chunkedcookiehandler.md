---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: f5592e0fd02d34b2882182196e0aa9425672a8fe
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244938"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="71fbc-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="71fbc-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="71fbc-103">Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="71fbc-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="71fbc-104">Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".</span><span class="sxs-lookup"><span data-stu-id="71fbc-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="71fbc-105">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="71fbc-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="71fbc-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="71fbc-106">\<federationConfiguration></span></span>  
<span data-ttu-id="71fbc-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="71fbc-107">\<cookieHandler></span></span>  
<span data-ttu-id="71fbc-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="71fbc-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71fbc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71fbc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71fbc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="71fbc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71fbc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="71fbc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71fbc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="71fbc-112">Attributes</span></span>  
  
|<span data-ttu-id="71fbc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="71fbc-113">Attribute</span></span>|<span data-ttu-id="71fbc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71fbc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71fbc-115">ChunkSize</span><span class="sxs-lookup"><span data-stu-id="71fbc-115">chunkSize</span></span>|<span data-ttu-id="71fbc-116">Le dimensioni massime, in caratteri, i dati di cookie HTTP per di un cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="71fbc-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="71fbc-117">È necessario prestare attenzione quando si modifica la dimensione del blocco.</span><span class="sxs-lookup"><span data-stu-id="71fbc-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="71fbc-118">Web browser hanno diversi limiti sulle dimensioni del cookie e il numero consentito per ogni dominio.</span><span class="sxs-lookup"><span data-stu-id="71fbc-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="71fbc-119">Ad esempio, la specifica di Netscape originale stipulata questi limiti: totale 300 cookie, 4096 byte per ogni intestazione del cookie (inclusi i metadati, non solo il valore del cookie) e i 20 cookie per ogni dominio.</span><span class="sxs-lookup"><span data-stu-id="71fbc-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="71fbc-120">Il valore predefinito è 2000.</span><span class="sxs-lookup"><span data-stu-id="71fbc-120">The default is 2000.</span></span> <span data-ttu-id="71fbc-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="71fbc-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71fbc-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="71fbc-122">Child Elements</span></span>  
 <span data-ttu-id="71fbc-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="71fbc-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71fbc-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="71fbc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="71fbc-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="71fbc-125">Element</span></span>|<span data-ttu-id="71fbc-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71fbc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71fbc-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="71fbc-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="71fbc-128">Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) utilizzato per leggere e scrivere i cookie.</span><span class="sxs-lookup"><span data-stu-id="71fbc-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71fbc-129">Note</span><span class="sxs-lookup"><span data-stu-id="71fbc-129">Remarks</span></span>  
 <span data-ttu-id="71fbc-130">Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> impostando la `mode` attributo delle `<cookieHandler>` elemento "Default" o "Chunked", è possibile specificare la dimensione di blocco che il gestore di cookie viene utilizzato per leggere e scrivere i cookie, includendo un `<chunkedCookieHandler>` elemento figlio e l'impostazione relativa `chunkSize` attributo.</span><span class="sxs-lookup"><span data-stu-id="71fbc-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="71fbc-131">Se il `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione di blocco predefinito di 2000 byte.</span><span class="sxs-lookup"><span data-stu-id="71fbc-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="71fbc-132">Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="71fbc-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="71fbc-133">Il `<chunkedCookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.</span><span class="sxs-lookup"><span data-stu-id="71fbc-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71fbc-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="71fbc-134">Example</span></span>  
 <span data-ttu-id="71fbc-135">L'esempio seguente configura un gestore di cookie chunked che scrive i cookie in blocchi di 3000 byte.</span><span class="sxs-lookup"><span data-stu-id="71fbc-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="71fbc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71fbc-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
