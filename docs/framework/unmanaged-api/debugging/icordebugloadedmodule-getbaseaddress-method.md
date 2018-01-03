---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d71b1db35a9e2747e7e14787f385f42f98305c61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="2181e-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="2181e-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="2181e-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="2181e-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2181e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2181e-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2181e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2181e-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="2181e-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="2181e-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2181e-107">Note</span><span class="sxs-lookup"><span data-stu-id="2181e-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2181e-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2181e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2181e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2181e-109">Requirements</span></span>  
 <span data-ttu-id="2181e-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2181e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2181e-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2181e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2181e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2181e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2181e-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2181e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2181e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2181e-114">See Also</span></span>  
 [<span data-ttu-id="2181e-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="2181e-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="2181e-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2181e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
