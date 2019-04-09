---
title: Metodo ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081450"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="85509-102">Metodo ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="85509-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="85509-103">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="85509-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85509-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85509-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85509-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85509-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="85509-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="85509-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85509-107">Note</span><span class="sxs-lookup"><span data-stu-id="85509-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85509-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="85509-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85509-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85509-109">Requirements</span></span>  
 <span data-ttu-id="85509-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85509-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85509-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85509-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85509-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85509-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="85509-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="85509-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85509-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85509-114">See also</span></span>

- [<span data-ttu-id="85509-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="85509-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="85509-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="85509-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
