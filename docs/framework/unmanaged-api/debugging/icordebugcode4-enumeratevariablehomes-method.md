---
title: Metodo ICorDebugCode4::EnumerateVariableHomes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1478ed89c216f9cd520bf1122571f09024283ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="4b454-102">Metodo ICorDebugCode4::EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="4b454-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="4b454-103">Ottiene un enumeratore per le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="4b454-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b454-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b454-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b454-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b454-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4b454-106">Un puntatore all'indirizzo di un [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) oggetto dell'interfaccia che è un enumeratore per le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="4b454-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b454-107">Note</span><span class="sxs-lookup"><span data-stu-id="4b454-107">Remarks</span></span>  
 <span data-ttu-id="4b454-108">Il [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) oggetto dell'interfaccia è un enumeratore standard derivato dall'interfaccia di "ICorDebugEnum" che consente di enumerare [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="4b454-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="4b454-109">La raccolta può includere più [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetti per l'indice stesso slot o un argomento se dispongono di case diversi in momenti diversi nella funzione.</span><span class="sxs-lookup"><span data-stu-id="4b454-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b454-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b454-110">Requirements</span></span>  
 <span data-ttu-id="4b454-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b454-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b454-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4b454-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b454-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b454-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b454-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b454-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b454-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b454-115">See Also</span></span>  
 [<span data-ttu-id="4b454-116">Interfaccia ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="4b454-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 [<span data-ttu-id="4b454-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4b454-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
