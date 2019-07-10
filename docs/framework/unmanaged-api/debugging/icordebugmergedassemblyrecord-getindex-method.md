---
title: Metodo ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c869c829acbfb9b0281537c7355229acbf2c5a7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752716"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="66734-102">Metodo ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="66734-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="66734-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="66734-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66734-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66734-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66734-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66734-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="66734-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="66734-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66734-107">Note</span><span class="sxs-lookup"><span data-stu-id="66734-107">Remarks</span></span>  
 <span data-ttu-id="66734-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="66734-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66734-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66734-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66734-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66734-110">Requirements</span></span>  
 <span data-ttu-id="66734-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66734-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66734-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66734-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66734-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66734-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66734-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66734-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66734-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66734-115">See also</span></span>

- [<span data-ttu-id="66734-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="66734-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="66734-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="66734-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
