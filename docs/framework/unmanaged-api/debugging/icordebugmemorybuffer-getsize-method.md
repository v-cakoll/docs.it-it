---
title: Metodo ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0db104dbfa61b836aa01b99be45725ed4c04c798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752785"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="d7ec5-102">Metodo ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="d7ec5-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="d7ec5-103">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="d7ec5-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ec5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7ec5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7ec5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7ec5-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="d7ec5-106">[out] Puntatore alle dimensioni del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="d7ec5-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7ec5-107">Note</span><span class="sxs-lookup"><span data-stu-id="d7ec5-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7ec5-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7ec5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7ec5-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7ec5-109">Requirements</span></span>  
 <span data-ttu-id="d7ec5-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7ec5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ec5-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7ec5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7ec5-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7ec5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7ec5-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7ec5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ec5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7ec5-114">See also</span></span>

- [<span data-ttu-id="d7ec5-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="d7ec5-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d7ec5-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d7ec5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
