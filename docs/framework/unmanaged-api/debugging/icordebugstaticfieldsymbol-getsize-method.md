---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154323"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="e3bb1-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="e3bb1-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="e3bb1-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="e3bb1-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3bb1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3bb1-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3bb1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e3bb1-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="e3bb1-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="e3bb1-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3bb1-107">Note</span><span class="sxs-lookup"><span data-stu-id="e3bb1-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3bb1-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e3bb1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3bb1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3bb1-109">Requirements</span></span>  
 <span data-ttu-id="e3bb1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3bb1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3bb1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3bb1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3bb1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3bb1-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e3bb1-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e3bb1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3bb1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3bb1-114">See also</span></span>

- [<span data-ttu-id="e3bb1-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e3bb1-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e3bb1-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e3bb1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
