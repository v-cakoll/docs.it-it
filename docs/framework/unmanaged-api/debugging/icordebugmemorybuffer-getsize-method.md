---
title: Metodo ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf95e0b5c8d4ae942bb428f53d4e58313e0e78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414752"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="f4198-102">Metodo ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="f4198-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="f4198-103">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="f4198-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4198-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4198-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4198-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4198-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="f4198-106">[out] Puntatore alle dimensioni del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="f4198-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4198-107">Note</span><span class="sxs-lookup"><span data-stu-id="f4198-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4198-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f4198-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4198-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4198-109">Requirements</span></span>  
 <span data-ttu-id="f4198-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4198-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4198-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f4198-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4198-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f4198-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4198-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4198-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4198-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4198-114">See Also</span></span>  
 [<span data-ttu-id="f4198-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="f4198-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="f4198-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f4198-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
