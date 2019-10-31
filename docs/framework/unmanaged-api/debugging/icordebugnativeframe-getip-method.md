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
ms.openlocfilehash: 3011a8c7e5cf278768587633967b2e9491cf87ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137331"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="39d47-102">Metodo ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="39d47-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="39d47-103">Ottiene la posizione di offset del codice nativo a cui è attualmente impostato il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="39d47-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39d47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39d47-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39d47-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="39d47-106">out Puntatore alla posizione di offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="39d47-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39d47-107">Note</span><span class="sxs-lookup"><span data-stu-id="39d47-107">Remarks</span></span>  
 <span data-ttu-id="39d47-108">Se la stack frame rappresentata da questo "ICorDebugNativeFrame" è attiva, l'offset corrisponde all'indirizzo dell'istruzione successiva da eseguire.</span><span class="sxs-lookup"><span data-stu-id="39d47-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="39d47-109">Se questo stack frame non è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire quando il stack frame viene riattivato.</span><span class="sxs-lookup"><span data-stu-id="39d47-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39d47-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39d47-110">Requirements</span></span>  
 <span data-ttu-id="39d47-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39d47-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d47-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39d47-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39d47-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39d47-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39d47-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d47-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d47-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39d47-115">See also</span></span>
