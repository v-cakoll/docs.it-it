---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c77ac2eac1022fa591066901f48eaf609b5367af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413563"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="03534-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="03534-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="03534-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="03534-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03534-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03534-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03534-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03534-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="03534-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="03534-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03534-107">Note</span><span class="sxs-lookup"><span data-stu-id="03534-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03534-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="03534-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03534-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03534-109">Requirements</span></span>  
 <span data-ttu-id="03534-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03534-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03534-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="03534-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03534-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="03534-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03534-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03534-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03534-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03534-114">See Also</span></span>  
 [<span data-ttu-id="03534-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="03534-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="03534-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="03534-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
