---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: 330496d5f0f80affcb6bc44a1f66f4321a635f00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580590"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="e9122-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="e9122-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="e9122-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="e9122-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9122-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9122-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e9122-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9122-105">Methods</span></span>  
 <span data-ttu-id="e9122-106">La classe BinaryMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e9122-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e9122-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e9122-107">Properties</span></span>  
 <span data-ttu-id="e9122-108">La classe BinaryMessageEncodingBindingElement dispone delle proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="e9122-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="e9122-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e9122-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="e9122-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e9122-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e9122-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9122-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9122-112">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="e9122-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="e9122-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e9122-113">MaxSessionSize</span></span>  
 <span data-ttu-id="e9122-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e9122-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e9122-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9122-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9122-116">Valore che specifica la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="e9122-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="e9122-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e9122-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="e9122-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e9122-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e9122-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9122-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9122-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="e9122-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="e9122-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="e9122-121">ReaderQuotas</span></span>  
 <span data-ttu-id="e9122-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="e9122-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="e9122-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9122-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9122-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="e9122-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9122-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9122-125">Requirements</span></span>  
  
|<span data-ttu-id="e9122-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e9122-126">MOF</span></span>|<span data-ttu-id="e9122-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e9122-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e9122-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e9122-128">Namespace</span></span>|<span data-ttu-id="e9122-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e9122-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9122-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9122-130">See also</span></span>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
