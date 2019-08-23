---
title: Metodo ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d41b99d7410333cb6a22443271c1fcbc41c3594
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962706"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="bb1a0-102">Metodo ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="bb1a0-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="bb1a0-103">Ottiene l'indirizzo di un campo statico.</span><span class="sxs-lookup"><span data-stu-id="bb1a0-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb1a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb1a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb1a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb1a0-105">Parameters</span></span>  
 <span data-ttu-id="bb1a0-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="bb1a0-106">pRVA</span></span>  
 <span data-ttu-id="bb1a0-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) del campo statico.</span><span class="sxs-lookup"><span data-stu-id="bb1a0-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb1a0-108">Note</span><span class="sxs-lookup"><span data-stu-id="bb1a0-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb1a0-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bb1a0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb1a0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb1a0-110">Requirements</span></span>  
 <span data-ttu-id="bb1a0-111">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb1a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb1a0-112">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bb1a0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb1a0-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb1a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb1a0-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb1a0-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1a0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb1a0-115">See also</span></span>

- [<span data-ttu-id="bb1a0-116">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="bb1a0-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="bb1a0-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb1a0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
