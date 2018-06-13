---
title: Metodo ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b877bde80b59b7d2074e4d799653dedd5aaacf39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419253"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="c1a9d-102">Metodo ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="c1a9d-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="c1a9d-103">Ottiene l'indirizzo di un campo statico.</span><span class="sxs-lookup"><span data-stu-id="c1a9d-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1a9d-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1a9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1a9d-105">Parameters</span></span>  
 <span data-ttu-id="c1a9d-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="c1a9d-106">pRVA</span></span>  
 <span data-ttu-id="c1a9d-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) del campo statico.</span><span class="sxs-lookup"><span data-stu-id="c1a9d-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1a9d-108">Note</span><span class="sxs-lookup"><span data-stu-id="c1a9d-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1a9d-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c1a9d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a9d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1a9d-110">Requirements</span></span>  
 <span data-ttu-id="c1a9d-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1a9d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a9d-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c1a9d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1a9d-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c1a9d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1a9d-114">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a9d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a9d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1a9d-115">See Also</span></span>  
 [<span data-ttu-id="c1a9d-116">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="c1a9d-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="c1a9d-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c1a9d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
