---
title: Metodo ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0901e64a7da7f68b2fbcdb63636503893263435f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413790"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="6b28a-102">Metodo ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="6b28a-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="6b28a-103">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="6b28a-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b28a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b28a-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b28a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b28a-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="6b28a-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="6b28a-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b28a-107">Note</span><span class="sxs-lookup"><span data-stu-id="6b28a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b28a-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6b28a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b28a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b28a-109">Requirements</span></span>  
 <span data-ttu-id="6b28a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b28a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b28a-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6b28a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b28a-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6b28a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b28a-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b28a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b28a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b28a-114">See Also</span></span>  
 [<span data-ttu-id="6b28a-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6b28a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="6b28a-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6b28a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
