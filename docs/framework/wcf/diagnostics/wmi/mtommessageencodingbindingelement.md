---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cc36d7daed1a2cfaf050cbfe9661951117ff66d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="11c9c-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="11c9c-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="11c9c-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="11c9c-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c9c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11c9c-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="11c9c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="11c9c-105">Methods</span></span>  
 <span data-ttu-id="11c9c-106">La classe MtomMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="11c9c-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="11c9c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="11c9c-107">Properties</span></span>  
 <span data-ttu-id="11c9c-108">La classe MtomMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="11c9c-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="11c9c-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="11c9c-109">Encoding</span></span>  
 <span data-ttu-id="11c9c-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="11c9c-110">Data type: string</span></span>  
  
 <span data-ttu-id="11c9c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="11c9c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11c9c-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="11c9c-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="11c9c-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="11c9c-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="11c9c-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="11c9c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="11c9c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="11c9c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11c9c-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="11c9c-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="11c9c-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="11c9c-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="11c9c-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="11c9c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="11c9c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="11c9c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11c9c-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="11c9c-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="11c9c-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="11c9c-121">ReaderQuotas</span></span>  
 <span data-ttu-id="11c9c-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="11c9c-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="11c9c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="11c9c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11c9c-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="11c9c-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c9c-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11c9c-125">Requirements</span></span>  
  
|<span data-ttu-id="11c9c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="11c9c-126">MOF</span></span>|<span data-ttu-id="11c9c-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="11c9c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="11c9c-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="11c9c-128">Namespace</span></span>|<span data-ttu-id="11c9c-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11c9c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11c9c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11c9c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
