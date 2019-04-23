---
title: Metodo ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081450"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="43d62-102">Metodo ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="43d62-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="43d62-103">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="43d62-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43d62-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43d62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43d62-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="43d62-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="43d62-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d62-107">Note</span><span class="sxs-lookup"><span data-stu-id="43d62-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43d62-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="43d62-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d62-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43d62-109">Requirements</span></span>  
 <span data-ttu-id="43d62-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43d62-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d62-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43d62-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43d62-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43d62-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43d62-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d62-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d62-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43d62-114">See also</span></span>

- [<span data-ttu-id="43d62-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="43d62-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="43d62-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="43d62-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
