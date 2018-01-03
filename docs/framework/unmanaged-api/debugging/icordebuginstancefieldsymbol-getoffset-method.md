---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ab38a19d2bd2d06f2a04d7efafcdad6956ad7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="e1d27-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="e1d27-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="e1d27-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="e1d27-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d27-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1d27-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1d27-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1d27-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="e1d27-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="e1d27-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1d27-107">Note</span><span class="sxs-lookup"><span data-stu-id="e1d27-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d27-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e1d27-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d27-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1d27-109">Requirements</span></span>  
 <span data-ttu-id="e1d27-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1d27-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d27-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e1d27-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1d27-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1d27-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1d27-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d27-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d27-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1d27-114">See Also</span></span>  
 [<span data-ttu-id="e1d27-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e1d27-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="e1d27-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e1d27-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
