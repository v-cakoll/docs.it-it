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
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213595"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="87891-102">Metodo ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="87891-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="87891-103">Ottiene la posizione di offset del codice nativo a cui è attualmente impostato il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="87891-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87891-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87891-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87891-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87891-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="87891-106">out Puntatore alla posizione di offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="87891-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87891-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="87891-107">Remarks</span></span>  
 <span data-ttu-id="87891-108">Se la stack frame rappresentata da questo "ICorDebugNativeFrame" è attiva, l'offset corrisponde all'indirizzo dell'istruzione successiva da eseguire.</span><span class="sxs-lookup"><span data-stu-id="87891-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="87891-109">Se questo stack frame non è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire quando il stack frame viene riattivato.</span><span class="sxs-lookup"><span data-stu-id="87891-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87891-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87891-110">Requirements</span></span>  
 <span data-ttu-id="87891-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87891-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87891-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87891-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87891-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87891-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87891-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87891-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87891-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87891-115">See also</span></span>
