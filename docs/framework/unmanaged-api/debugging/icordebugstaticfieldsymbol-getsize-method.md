---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb72a7d6c39efa5fa93bfddc314d07ec6cd8348
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419094"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="64349-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="64349-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="64349-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="64349-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64349-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64349-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64349-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64349-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="64349-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="64349-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64349-107">Note</span><span class="sxs-lookup"><span data-stu-id="64349-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64349-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="64349-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64349-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64349-109">Requirements</span></span>  
 <span data-ttu-id="64349-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64349-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64349-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="64349-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64349-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="64349-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64349-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64349-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64349-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64349-114">See Also</span></span>  
 [<span data-ttu-id="64349-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="64349-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="64349-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="64349-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
