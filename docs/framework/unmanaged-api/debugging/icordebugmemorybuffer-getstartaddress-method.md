---
title: Metodo ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212347"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="e8ae4-102">Metodo ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="e8ae4-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="e8ae4-103">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="e8ae4-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ae4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8ae4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ae4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8ae4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e8ae4-106">[out] Puntatore all'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="e8ae4-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8ae4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e8ae4-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="e8ae4-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e8ae4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ae4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8ae4-109">Requirements</span></span>  
 <span data-ttu-id="e8ae4-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ae4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ae4-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8ae4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8ae4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8ae4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8ae4-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ae4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ae4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ae4-114">See also</span></span>

- [<span data-ttu-id="e8ae4-115">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="e8ae4-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="e8ae4-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e8ae4-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
