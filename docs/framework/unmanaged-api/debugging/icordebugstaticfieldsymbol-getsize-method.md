---
title: Metodo ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379409"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="a2912-102">Metodo ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="a2912-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="a2912-103">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="a2912-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2912-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2912-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2912-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2912-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="a2912-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="a2912-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2912-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a2912-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2912-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a2912-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2912-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2912-109">Requirements</span></span>  
 <span data-ttu-id="a2912-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2912-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2912-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2912-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2912-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2912-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2912-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2912-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2912-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2912-114">See also</span></span>

- [<span data-ttu-id="a2912-115">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a2912-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="a2912-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2912-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
