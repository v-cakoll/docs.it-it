---
title: Metodo ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: d7ad4a6b25fe6d53ab0b21066345451ae7c22c16
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213322"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="4dda8-102">Metodo ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4dda8-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="4dda8-103">Ottiene il numero di istanze "ICorDebugModule" specificate da `celt` dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="4dda8-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dda8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4dda8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dda8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4dda8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4dda8-106">in Numero di `ICorDebugModule` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="4dda8-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="4dda8-107">out Matrice di puntatori, ciascuno dei quali punta a un `ICorDebugModule` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4dda8-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4dda8-108">out Puntatore al numero di `ICorDebugModule` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="4dda8-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="4dda8-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="4dda8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dda8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dda8-110">Requirements</span></span>  
 <span data-ttu-id="4dda8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dda8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dda8-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dda8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dda8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dda8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dda8-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dda8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dda8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dda8-115">See also</span></span>
