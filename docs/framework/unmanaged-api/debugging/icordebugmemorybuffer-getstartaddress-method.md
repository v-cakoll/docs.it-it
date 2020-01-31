---
title: Metodo ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793174"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="7251c-102">Metodo ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="7251c-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="7251c-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="7251c-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7251c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7251c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7251c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7251c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="7251c-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="7251c-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7251c-107">Note</span><span class="sxs-lookup"><span data-stu-id="7251c-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="7251c-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7251c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7251c-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7251c-109">Requirements</span></span>  
 <span data-ttu-id="7251c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7251c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7251c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7251c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7251c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7251c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7251c-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7251c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7251c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7251c-114">See also</span></span>

- [<span data-ttu-id="7251c-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="7251c-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="7251c-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7251c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
