---
title: Metodo ICorDebugMemoryBuffer::GetSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 658fb2ce289b4b8cabfcf0cc2ea5f8dace2ec754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="80684-102">Metodo ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="80684-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="80684-103">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="80684-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80684-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80684-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80684-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80684-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="80684-106">[out] Puntatore alle dimensioni del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="80684-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80684-107">Note</span><span class="sxs-lookup"><span data-stu-id="80684-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80684-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80684-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80684-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80684-109">Requirements</span></span>  
 <span data-ttu-id="80684-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80684-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80684-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="80684-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80684-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80684-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80684-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80684-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80684-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80684-114">See Also</span></span>  
 [<span data-ttu-id="80684-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="80684-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="80684-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="80684-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
