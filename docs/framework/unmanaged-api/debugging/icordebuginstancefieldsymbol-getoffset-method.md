---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 453f691f414050905f5d73e201ebeed79e2aaf50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910197"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="a4c7c-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="a4c7c-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="a4c7c-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="a4c7c-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4c7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4c7c-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="a4c7c-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="a4c7c-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4c7c-107">Note</span><span class="sxs-lookup"><span data-stu-id="a4c7c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4c7c-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a4c7c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c7c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4c7c-109">Requirements</span></span>  
 <span data-ttu-id="a4c7c-110">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4c7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c7c-111">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a4c7c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4c7c-112">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4c7c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4c7c-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4c7c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c7c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4c7c-114">See also</span></span>

- [<span data-ttu-id="a4c7c-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a4c7c-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a4c7c-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a4c7c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
