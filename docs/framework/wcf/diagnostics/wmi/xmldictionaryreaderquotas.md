---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="f8d05-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f8d05-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="f8d05-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f8d05-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8d05-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f8d05-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8d05-105">Methods</span></span>  
 <span data-ttu-id="f8d05-106">La classe XmlDictionaryReaderQuotas non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="f8d05-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f8d05-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f8d05-107">Properties</span></span>  
 <span data-ttu-id="f8d05-108">La classe XmlDictionaryReaderQuotas presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8d05-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="f8d05-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="f8d05-109">MaxArrayLength</span></span>  
 <span data-ttu-id="f8d05-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f8d05-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f8d05-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f8d05-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8d05-112">Lunghezza massima consentita della matrice.</span><span class="sxs-lookup"><span data-stu-id="f8d05-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="f8d05-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="f8d05-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="f8d05-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f8d05-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f8d05-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f8d05-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8d05-116">Byte massimi consentiti restituiti per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="f8d05-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="f8d05-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="f8d05-117">MaxDepth</span></span>  
 <span data-ttu-id="f8d05-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f8d05-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f8d05-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f8d05-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8d05-120">Profondità massima dei nodi annidati per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="f8d05-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="f8d05-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="f8d05-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="f8d05-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f8d05-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="f8d05-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f8d05-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8d05-124">Caratteri massimi consentiti in un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="f8d05-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="f8d05-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="f8d05-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="f8d05-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f8d05-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="f8d05-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f8d05-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8d05-128">Caratteri massimi consentiti nel contenuto di un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="f8d05-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d05-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8d05-129">Requirements</span></span>  
  
|<span data-ttu-id="f8d05-130">MOF</span><span class="sxs-lookup"><span data-stu-id="f8d05-130">MOF</span></span>|<span data-ttu-id="f8d05-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f8d05-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f8d05-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f8d05-132">Namespace</span></span>|<span data-ttu-id="f8d05-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f8d05-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8d05-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d05-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
