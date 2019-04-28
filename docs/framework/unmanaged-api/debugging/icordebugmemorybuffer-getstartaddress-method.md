---
title: 'Metodo icordebugmemorybuffer:: Getstartaddress'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916526"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="8953e-102">Metodo icordebugmemorybuffer:: Getstartaddress</span><span class="sxs-lookup"><span data-stu-id="8953e-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="8953e-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="8953e-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8953e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8953e-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8953e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8953e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8953e-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="8953e-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8953e-107">Note</span><span class="sxs-lookup"><span data-stu-id="8953e-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8953e-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8953e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8953e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8953e-109">Requirements</span></span>  
 <span data-ttu-id="8953e-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8953e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8953e-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8953e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8953e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8953e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8953e-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8953e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8953e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8953e-114">See also</span></span>

- [<span data-ttu-id="8953e-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="8953e-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="8953e-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8953e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
