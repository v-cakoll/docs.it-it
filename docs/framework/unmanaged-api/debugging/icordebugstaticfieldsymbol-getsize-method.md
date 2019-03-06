---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fed264da3767ffa74a1b61583639887adbea4a71
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490736"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="aef41-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="aef41-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="aef41-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="aef41-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aef41-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef41-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aef41-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="aef41-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="aef41-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aef41-107">Note</span><span class="sxs-lookup"><span data-stu-id="aef41-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aef41-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="aef41-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef41-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aef41-109">Requirements</span></span>  
 <span data-ttu-id="aef41-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aef41-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aef41-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aef41-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aef41-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aef41-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aef41-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aef41-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef41-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aef41-114">See also</span></span>
- [<span data-ttu-id="aef41-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="aef41-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="aef41-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="aef41-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
