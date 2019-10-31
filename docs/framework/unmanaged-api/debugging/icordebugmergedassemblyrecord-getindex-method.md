---
title: 'Metodo metodo icordebugmergedassemblyrecord:: GetIndex'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 236bd8b22d6c3ec783d787f6c906ede3193cfc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131412"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="ef86e-102">Metodo metodo icordebugmergedassemblyrecord:: GetIndex</span><span class="sxs-lookup"><span data-stu-id="ef86e-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="ef86e-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ef86e-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef86e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef86e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef86e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef86e-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="ef86e-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="ef86e-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef86e-107">Note</span><span class="sxs-lookup"><span data-stu-id="ef86e-107">Remarks</span></span>  
 <span data-ttu-id="ef86e-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="ef86e-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef86e-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ef86e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef86e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef86e-110">Requirements</span></span>  
 <span data-ttu-id="ef86e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef86e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef86e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef86e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef86e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef86e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef86e-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef86e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef86e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef86e-115">See also</span></span>

- [<span data-ttu-id="ef86e-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ef86e-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ef86e-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ef86e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
