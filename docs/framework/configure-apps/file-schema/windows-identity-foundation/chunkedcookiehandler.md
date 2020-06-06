---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252113"
---
# \<chunkedCookieHandler>
<span data-ttu-id="616f7-101">Configura <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="616f7-101">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="616f7-102">Questo elemento può essere presente solo se l' `mode` attributo dell' `<cookieHandler>` elemento è "default" o "Chunked".</span><span class="sxs-lookup"><span data-stu-id="616f7-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="616f7-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="616f7-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="616f7-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="616f7-104">Attributes and Elements</span></span>  
 <span data-ttu-id="616f7-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="616f7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="616f7-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="616f7-106">Attributes</span></span>  
  
|<span data-ttu-id="616f7-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="616f7-107">Attribute</span></span>|<span data-ttu-id="616f7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616f7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="616f7-109">chunkSize</span><span class="sxs-lookup"><span data-stu-id="616f7-109">chunkSize</span></span>|<span data-ttu-id="616f7-110">Dimensione massima, in caratteri, dei dati del cookie HTTP per un cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="616f7-110">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="616f7-111">È necessario prestare attenzione quando si modificano le dimensioni del blocco.</span><span class="sxs-lookup"><span data-stu-id="616f7-111">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="616f7-112">I Web browser hanno limiti diversi sulle dimensioni dei cookie e sul numero consentito per dominio.</span><span class="sxs-lookup"><span data-stu-id="616f7-112">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="616f7-113">Ad esempio, la specifica Netscape originale ha stabilito questi limiti: 300 cookie totali, 4096 byte per intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio.</span><span class="sxs-lookup"><span data-stu-id="616f7-113">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="616f7-114">Il valore predefinito è 2000.</span><span class="sxs-lookup"><span data-stu-id="616f7-114">The default is 2000.</span></span> <span data-ttu-id="616f7-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="616f7-115">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="616f7-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="616f7-116">Child Elements</span></span>  
 <span data-ttu-id="616f7-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="616f7-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="616f7-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="616f7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="616f7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="616f7-119">Element</span></span>|<span data-ttu-id="616f7-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616f7-120">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="616f7-121">Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> usato da (Sam) per la lettura e la scrittura dei cookie.</span><span class="sxs-lookup"><span data-stu-id="616f7-121">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="616f7-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="616f7-122">Remarks</span></span>  
 <span data-ttu-id="616f7-123">Quando si specifica un oggetto impostando <xref:System.IdentityModel.Services.ChunkedCookieHandler> l' `mode` attributo dell' `<cookieHandler>` elemento su "default" o "Chunked", è possibile specificare la dimensione del blocco utilizzata dal gestore di cookie per leggere e scrivere cookie includendo un `<chunkedCookieHandler>` elemento figlio e impostando il relativo `chunkSize` attributo.</span><span class="sxs-lookup"><span data-stu-id="616f7-123">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="616f7-124">Se l' `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione del blocco predefinita di 2000 byte.</span><span class="sxs-lookup"><span data-stu-id="616f7-124">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="616f7-125">Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="616f7-125">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="616f7-126">L' `<chunkedCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.</span><span class="sxs-lookup"><span data-stu-id="616f7-126">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="616f7-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="616f7-127">Example</span></span>  
 <span data-ttu-id="616f7-128">Nell'esempio seguente viene configurato un gestore di cookie Chunked che scrive cookie in blocchi di 3000 byte.</span><span class="sxs-lookup"><span data-stu-id="616f7-128">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="616f7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="616f7-129">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
