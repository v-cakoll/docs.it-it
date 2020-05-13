---
title: Metodo ICorDebugProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: d00a5f71ac7e47d78deebca0e46350e465964c72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210098"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="56034-102">Metodo ICorDebugProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="56034-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="56034-103">Ottiene il numero specificato di istanze di ICorDebugProcess dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="56034-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56034-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56034-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56034-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56034-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="56034-106">in Numero di `ICorDebugProcess` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="56034-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="56034-107">out Matrice di puntatori, ciascuno dei quali punta a un `ICorDebugProcess` oggetto che rappresenta un processo.</span><span class="sxs-lookup"><span data-stu-id="56034-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="56034-108">out Puntatore al numero di `ICorDebugProcess` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="56034-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="56034-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="56034-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56034-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56034-110">Requirements</span></span>  
 <span data-ttu-id="56034-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56034-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56034-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56034-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56034-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56034-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56034-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56034-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
