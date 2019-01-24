---
title: Metodo ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27a50e6fb120e537d28759a79a2b90c6d437e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600453"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="7be0b-102">Metodo ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="7be0b-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="7be0b-103">Ottiene il codice nativo offset posizione a cui è attualmente impostato il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7be0b-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7be0b-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7be0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7be0b-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="7be0b-106">[out] Puntatore alla posizione di offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7be0b-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be0b-107">Note</span><span class="sxs-lookup"><span data-stu-id="7be0b-107">Remarks</span></span>  
 <span data-ttu-id="7be0b-108">Se lo stack frame che è rappresentato da questo "ICorDebugNativeFrame" è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire.</span><span class="sxs-lookup"><span data-stu-id="7be0b-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="7be0b-109">Se lo stack frame corrente non è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire quando viene riattivato lo stack frame.</span><span class="sxs-lookup"><span data-stu-id="7be0b-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be0b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7be0b-110">Requirements</span></span>  
 <span data-ttu-id="7be0b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be0b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be0b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7be0b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7be0b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be0b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be0b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be0b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be0b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7be0b-115">See also</span></span>

