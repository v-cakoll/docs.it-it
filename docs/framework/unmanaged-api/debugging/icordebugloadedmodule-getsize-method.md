---
title: Metodo ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936866"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="413a8-102">Metodo ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="413a8-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="413a8-103">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="413a8-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="413a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="413a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="413a8-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="413a8-106">[out] Puntatore al numero di byte nel modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="413a8-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="413a8-107">Note</span><span class="sxs-lookup"><span data-stu-id="413a8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="413a8-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="413a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="413a8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="413a8-109">Requirements</span></span>  
 <span data-ttu-id="413a8-110">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="413a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="413a8-111">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="413a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="413a8-112">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="413a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="413a8-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413a8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413a8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="413a8-114">See also</span></span>

- [<span data-ttu-id="413a8-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="413a8-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="413a8-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="413a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
