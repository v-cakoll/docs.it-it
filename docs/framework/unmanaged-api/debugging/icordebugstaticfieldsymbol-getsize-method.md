---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d99e06c1093dbc67e9c1999e4b9ccabd6579340e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962670"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="5e17e-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="5e17e-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="5e17e-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="5e17e-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e17e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e17e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e17e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e17e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="5e17e-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="5e17e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e17e-107">Note</span><span class="sxs-lookup"><span data-stu-id="5e17e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e17e-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5e17e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e17e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e17e-109">Requirements</span></span>  
 <span data-ttu-id="5e17e-110">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e17e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e17e-111">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5e17e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e17e-112">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e17e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e17e-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e17e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e17e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e17e-114">See also</span></span>

- [<span data-ttu-id="5e17e-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5e17e-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="5e17e-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5e17e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
