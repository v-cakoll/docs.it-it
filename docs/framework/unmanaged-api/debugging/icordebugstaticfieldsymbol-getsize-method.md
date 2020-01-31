---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: deeb887dad38417e3ebb980f5ef2f89392388d65
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791812"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="ea81d-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="ea81d-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="ea81d-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="ea81d-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea81d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea81d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea81d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea81d-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="ea81d-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="ea81d-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea81d-107">Note</span><span class="sxs-lookup"><span data-stu-id="ea81d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea81d-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ea81d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea81d-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ea81d-109">Requirements</span></span>  
 <span data-ttu-id="ea81d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea81d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea81d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea81d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea81d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea81d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea81d-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea81d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea81d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea81d-114">See also</span></span>

- [<span data-ttu-id="ea81d-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ea81d-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ea81d-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ea81d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
