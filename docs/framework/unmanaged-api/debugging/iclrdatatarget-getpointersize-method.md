---
title: Metodo ICLRDataTarget::GetPointerSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ca35246b82ed4adc982b6e7b157398d230dabe4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="3837a-102">Metodo ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="3837a-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="3837a-103">Ottiene le dimensioni, in byte, del tipo di puntatore utilizzata dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3837a-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="3837a-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3837a-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3837a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3837a-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3837a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3837a-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="3837a-107">[out] Puntatore a un valore intero che specifica la dimensione, in byte, di un puntatore sul processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3837a-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3837a-108">Note</span><span class="sxs-lookup"><span data-stu-id="3837a-108">Remarks</span></span>  
 <span data-ttu-id="3837a-109">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="3837a-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3837a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3837a-110">Requirements</span></span>  
 <span data-ttu-id="3837a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3837a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3837a-112">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="3837a-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3837a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3837a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3837a-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3837a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3837a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3837a-115">See Also</span></span>  
 [<span data-ttu-id="3837a-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3837a-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
