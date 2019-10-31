---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 8af814ff2eaaf3ae6dae9031c13bf37ea0c1236b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122648"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="73052-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="73052-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="73052-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="73052-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73052-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73052-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73052-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73052-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="73052-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="73052-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73052-107">Note</span><span class="sxs-lookup"><span data-stu-id="73052-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73052-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="73052-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73052-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73052-109">Requirements</span></span>  
 <span data-ttu-id="73052-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73052-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73052-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73052-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73052-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73052-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73052-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73052-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73052-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73052-114">See also</span></span>

- [<span data-ttu-id="73052-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="73052-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="73052-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="73052-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
