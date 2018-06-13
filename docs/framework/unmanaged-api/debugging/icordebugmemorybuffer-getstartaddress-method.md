---
title: Metodo ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422933"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="bbe32-102">Metodo ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="bbe32-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="bbe32-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="bbe32-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbe32-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbe32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bbe32-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bbe32-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="bbe32-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe32-107">Note</span><span class="sxs-lookup"><span data-stu-id="bbe32-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bbe32-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bbe32-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe32-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bbe32-109">Requirements</span></span>  
 <span data-ttu-id="bbe32-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe32-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe32-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bbe32-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbe32-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bbe32-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbe32-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe32-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe32-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe32-114">See Also</span></span>  
 [<span data-ttu-id="bbe32-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="bbe32-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="bbe32-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bbe32-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
