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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f80b9ac7ca052ea3a8d7d89b35413b167eacfa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="97b5e-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="97b5e-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="97b5e-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="97b5e-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97b5e-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="97b5e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="97b5e-105">Methods</span></span>  
 <span data-ttu-id="97b5e-106">La classe BinaryMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="97b5e-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97b5e-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="97b5e-107">Properties</span></span>  
 <span data-ttu-id="97b5e-108">La classe BinaryMessageEncodingBindingElement dispone delle proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="97b5e-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="97b5e-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="97b5e-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="97b5e-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="97b5e-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="97b5e-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97b5e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97b5e-112">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="97b5e-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="97b5e-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="97b5e-113">MaxSessionSize</span></span>  
 <span data-ttu-id="97b5e-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="97b5e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="97b5e-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97b5e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97b5e-116">Valore che specifica la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="97b5e-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="97b5e-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="97b5e-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="97b5e-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="97b5e-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="97b5e-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97b5e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97b5e-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="97b5e-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="97b5e-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="97b5e-121">ReaderQuotas</span></span>  
 <span data-ttu-id="97b5e-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="97b5e-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="97b5e-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97b5e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97b5e-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="97b5e-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b5e-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97b5e-125">Requirements</span></span>  
  
|<span data-ttu-id="97b5e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="97b5e-126">MOF</span></span>|<span data-ttu-id="97b5e-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="97b5e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="97b5e-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="97b5e-128">Namespace</span></span>|<span data-ttu-id="97b5e-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="97b5e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97b5e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97b5e-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
