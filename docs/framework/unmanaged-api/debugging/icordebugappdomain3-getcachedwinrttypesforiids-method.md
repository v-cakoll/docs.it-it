---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ef8d1c47275d3cbd69c1516b788b950f8535513
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737713"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="55cf8-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="55cf8-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="55cf8-103">Ottiene un enumeratore per i tipi Windows Runtime memorizzato nella cache in un dominio di applicazione basato su identificatori relativi interfaccia.</span><span class="sxs-lookup"><span data-stu-id="55cf8-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55cf8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55cf8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55cf8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55cf8-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="55cf8-106">[in] Il numero di tipi richiesti.</span><span class="sxs-lookup"><span data-stu-id="55cf8-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="55cf8-107">[in] Puntatore a una matrice contenente gli identificatori di interfaccia corrispondenti per le rappresentazioni gestite dei tipi Windows Runtime da recuperare.</span><span class="sxs-lookup"><span data-stu-id="55cf8-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="55cf8-108">[out] Un puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugTypeEnum" che consente l'enumerazione delle rappresentazioni gestite memorizzato nella cache dei tipi Windows Runtime recuperati in base gli identificatori di interfaccia in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="55cf8-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55cf8-109">Note</span><span class="sxs-lookup"><span data-stu-id="55cf8-109">Remarks</span></span>  
 <span data-ttu-id="55cf8-110">Se il metodo non riesce a recuperare le informazioni per un identificatore di interfaccia specifica, la voce corrispondente nella raccolta "ICorDebugTypeEnum" sarà un tipo `ELEMENT_TYPE_END` per gli errori a causa di problemi di recupero dei dati, o `ELEMENT_TYPE_VOID` per interfaccia sconosciuto identificatori.</span><span class="sxs-lookup"><span data-stu-id="55cf8-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55cf8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55cf8-111">Requirements</span></span>  
 <span data-ttu-id="55cf8-112">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="55cf8-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="55cf8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55cf8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55cf8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55cf8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55cf8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55cf8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cf8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55cf8-116">See also</span></span>

- [<span data-ttu-id="55cf8-117">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="55cf8-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
