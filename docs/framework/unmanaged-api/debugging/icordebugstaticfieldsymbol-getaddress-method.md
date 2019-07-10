---
title: Metodo ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a45f233fdec23a504a71a68370e9da8e38ac0bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760865"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="ab949-102">Metodo ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="ab949-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="ab949-103">Ottiene l'indirizzo di un campo statico.</span><span class="sxs-lookup"><span data-stu-id="ab949-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab949-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab949-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab949-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab949-105">Parameters</span></span>  
 <span data-ttu-id="ab949-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="ab949-106">pRVA</span></span>  
 <span data-ttu-id="ab949-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) del campo statico.</span><span class="sxs-lookup"><span data-stu-id="ab949-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab949-108">Note</span><span class="sxs-lookup"><span data-stu-id="ab949-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab949-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ab949-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab949-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab949-110">Requirements</span></span>  
 <span data-ttu-id="ab949-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab949-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab949-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab949-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab949-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab949-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab949-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab949-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab949-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab949-115">See also</span></span>

- [<span data-ttu-id="ab949-116">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ab949-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ab949-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ab949-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
