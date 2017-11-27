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
ms.openlocfilehash: dac64c785077fc3901e712498e66e11b9c9f3279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="e2501-102">Metodo ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="e2501-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="e2501-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e2501-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2501-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2501-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2501-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2501-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="e2501-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="e2501-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2501-107">Note</span><span class="sxs-lookup"><span data-stu-id="e2501-107">Remarks</span></span>  
 <span data-ttu-id="e2501-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="e2501-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2501-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2501-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2501-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2501-110">Requirements</span></span>  
 <span data-ttu-id="e2501-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2501-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2501-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e2501-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2501-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2501-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2501-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2501-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2501-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2501-115">See Also</span></span>  
 [<span data-ttu-id="e2501-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="e2501-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="e2501-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e2501-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
