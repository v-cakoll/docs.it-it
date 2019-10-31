---
title: 'Metodo ICorDebugInstanceFieldSymbol:: GetOffset'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 3886e29a1c2fd44fbe50d1eef722f99da7abdbe5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139006"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="dcc70-102">Metodo ICorDebugInstanceFieldSymbol:: GetOffset</span><span class="sxs-lookup"><span data-stu-id="dcc70-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="dcc70-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="dcc70-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcc70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcc70-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcc70-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="dcc70-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="dcc70-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc70-107">Note</span><span class="sxs-lookup"><span data-stu-id="dcc70-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcc70-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dcc70-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc70-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcc70-109">Requirements</span></span>  
 <span data-ttu-id="dcc70-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc70-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc70-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcc70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcc70-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcc70-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcc70-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc70-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc70-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcc70-114">See also</span></span>

- [<span data-ttu-id="dcc70-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="dcc70-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="dcc70-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dcc70-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
