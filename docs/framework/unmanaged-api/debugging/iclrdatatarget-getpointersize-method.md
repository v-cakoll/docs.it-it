---
title: Metodo ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54abcd357c6f26f54432b39bfcb4a0d63afabfe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738719"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="f7b81-102">Metodo ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="f7b81-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="f7b81-103">Ottiene la dimensione, espressa in byte, del tipo di puntatore che viene utilizzato il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f7b81-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="f7b81-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f7b81-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b81-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7b81-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7b81-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7b81-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="f7b81-107">[out] Un puntatore a un valore intero che specifica la dimensione, espressa in byte, dell'indicatore di misura sul processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f7b81-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7b81-108">Note</span><span class="sxs-lookup"><span data-stu-id="f7b81-108">Remarks</span></span>  
 <span data-ttu-id="f7b81-109">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="f7b81-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b81-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7b81-110">Requirements</span></span>  
 <span data-ttu-id="f7b81-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b81-112">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f7b81-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f7b81-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7b81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7b81-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b81-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b81-115">See also</span></span>

- [<span data-ttu-id="f7b81-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f7b81-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
