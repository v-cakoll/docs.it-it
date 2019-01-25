---
title: Metodo ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29149ceb155cdfdf7b735d6939809e80f2ba4dc0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695543"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="4bf58-102">Metodo ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="4bf58-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="4bf58-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="4bf58-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bf58-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bf58-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bf58-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="4bf58-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="4bf58-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bf58-107">Note</span><span class="sxs-lookup"><span data-stu-id="4bf58-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4bf58-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4bf58-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf58-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bf58-109">Requirements</span></span>  
 <span data-ttu-id="4bf58-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf58-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf58-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bf58-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bf58-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bf58-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bf58-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf58-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf58-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bf58-114">See also</span></span>
- [<span data-ttu-id="4bf58-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="4bf58-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="4bf58-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4bf58-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
