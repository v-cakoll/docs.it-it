---
title: Metodo ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5984addb41c33468068f7ad24a15533f75dc367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714724"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="ec678-102">Metodo ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="ec678-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="ec678-103">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="ec678-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec678-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec678-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec678-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec678-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="ec678-106">[out] Puntatore alle dimensioni del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="ec678-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec678-107">Note</span><span class="sxs-lookup"><span data-stu-id="ec678-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec678-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ec678-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec678-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec678-109">Requirements</span></span>  
 <span data-ttu-id="ec678-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec678-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec678-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec678-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec678-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec678-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec678-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec678-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec678-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec678-114">See also</span></span>
- [<span data-ttu-id="ec678-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="ec678-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="ec678-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ec678-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
