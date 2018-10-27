---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: 326fe6a7ca8dc5dba0dd64b1c5fc97cec49279c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180883"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="55a85-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="55a85-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="55a85-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="55a85-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55a85-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="55a85-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="55a85-105">Methods</span></span>  
 <span data-ttu-id="55a85-106">La classe BinaryMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="55a85-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="55a85-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="55a85-107">Properties</span></span>  
 <span data-ttu-id="55a85-108">La classe BinaryMessageEncodingBindingElement dispone delle proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="55a85-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="55a85-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="55a85-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="55a85-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="55a85-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="55a85-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55a85-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55a85-112">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="55a85-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="55a85-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="55a85-113">MaxSessionSize</span></span>  
 <span data-ttu-id="55a85-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="55a85-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="55a85-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55a85-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55a85-116">Valore che specifica la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="55a85-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="55a85-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="55a85-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="55a85-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="55a85-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="55a85-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55a85-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55a85-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="55a85-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="55a85-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="55a85-121">ReaderQuotas</span></span>  
 <span data-ttu-id="55a85-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="55a85-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="55a85-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="55a85-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55a85-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="55a85-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a85-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55a85-125">Requirements</span></span>  
  
|<span data-ttu-id="55a85-126">MOF</span><span class="sxs-lookup"><span data-stu-id="55a85-126">MOF</span></span>|<span data-ttu-id="55a85-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="55a85-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="55a85-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="55a85-128">Namespace</span></span>|<span data-ttu-id="55a85-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="55a85-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55a85-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55a85-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
