---
title: 'Metodo ICorDebugMemoryBuffer:: GetStartAddress'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127993"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="10a8b-102">Metodo ICorDebugMemoryBuffer:: GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="10a8b-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="10a8b-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="10a8b-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10a8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a8b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10a8b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="10a8b-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="10a8b-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10a8b-107">Note</span><span class="sxs-lookup"><span data-stu-id="10a8b-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="10a8b-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="10a8b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a8b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10a8b-109">Requirements</span></span>  
 <span data-ttu-id="10a8b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a8b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a8b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10a8b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10a8b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10a8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10a8b-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a8b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a8b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10a8b-114">See also</span></span>

- [<span data-ttu-id="10a8b-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="10a8b-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="10a8b-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="10a8b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
