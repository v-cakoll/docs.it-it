---
title: Metodo ICorDebugLoadedModule::GetSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fb340845afac0f5a13f7c4646d11ac057ebd054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="83fd2-102">Metodo ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="83fd2-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="83fd2-103">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="83fd2-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83fd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83fd2-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83fd2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83fd2-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="83fd2-106">[out] Puntatore al numero di byte nel modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="83fd2-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83fd2-107">Note</span><span class="sxs-lookup"><span data-stu-id="83fd2-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83fd2-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="83fd2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83fd2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83fd2-109">Requirements</span></span>  
 <span data-ttu-id="83fd2-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83fd2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83fd2-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="83fd2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83fd2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83fd2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83fd2-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83fd2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fd2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83fd2-114">See Also</span></span>  
 [<span data-ttu-id="83fd2-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="83fd2-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="83fd2-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="83fd2-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
