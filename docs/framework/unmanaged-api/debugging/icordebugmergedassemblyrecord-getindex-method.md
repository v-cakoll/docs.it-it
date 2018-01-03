---
title: Metodo ICorDebugMergedAssemblyRecord::GetIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54ff8d6935f5507ab02d9d566921cb7f8a890bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="9da89-102">Metodo ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="9da89-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="9da89-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9da89-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9da89-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9da89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9da89-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="9da89-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="9da89-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9da89-107">Note</span><span class="sxs-lookup"><span data-stu-id="9da89-107">Remarks</span></span>  
 <span data-ttu-id="9da89-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="9da89-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9da89-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9da89-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da89-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9da89-110">Requirements</span></span>  
 <span data-ttu-id="9da89-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da89-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9da89-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9da89-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9da89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9da89-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da89-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da89-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9da89-115">See Also</span></span>  
 [<span data-ttu-id="9da89-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="9da89-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="9da89-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9da89-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
