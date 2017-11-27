---
title: BinaryMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 09d43ed76ef70f4478aa1029c254a7b1686a8d08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="e3c76-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="e3c76-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="e3c76-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="e3c76-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c76-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3c76-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e3c76-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e3c76-105">Methods</span></span>  
 <span data-ttu-id="e3c76-106">La classe BinaryMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e3c76-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e3c76-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e3c76-107">Properties</span></span>  
 <span data-ttu-id="e3c76-108">La classe BinaryMessageEncodingBindingElement dispone delle proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="e3c76-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="e3c76-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e3c76-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="e3c76-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e3c76-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e3c76-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e3c76-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3c76-112">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="e3c76-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="e3c76-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e3c76-113">MaxSessionSize</span></span>  
 <span data-ttu-id="e3c76-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e3c76-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e3c76-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e3c76-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3c76-116">Valore che specifica la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="e3c76-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="e3c76-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e3c76-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="e3c76-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e3c76-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e3c76-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e3c76-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3c76-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="e3c76-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="e3c76-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="e3c76-121">ReaderQuotas</span></span>  
 <span data-ttu-id="e3c76-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="e3c76-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="e3c76-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e3c76-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3c76-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="e3c76-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c76-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3c76-125">Requirements</span></span>  
  
|<span data-ttu-id="e3c76-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e3c76-126">MOF</span></span>|<span data-ttu-id="e3c76-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e3c76-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e3c76-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e3c76-128">Namespace</span></span>|<span data-ttu-id="e3c76-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e3c76-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3c76-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3c76-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
