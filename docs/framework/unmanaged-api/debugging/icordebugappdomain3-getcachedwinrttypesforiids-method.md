---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84b58e3a016431eba10710ea384338cb388404ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="3fdd1-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="3fdd1-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="3fdd1-103">Ottiene un enumeratore per memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] basato su tipi in un dominio applicazione in base ai relativi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3fdd1-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fdd1-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fdd1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fdd1-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="3fdd1-106">[in] Il numero di tipi richiesti.</span><span class="sxs-lookup"><span data-stu-id="3fdd1-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="3fdd1-107">[in] Un puntatore a una matrice che contiene gli identificatori di interfaccia corrispondenti per le rappresentazioni di gestito il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3fdd1-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="3fdd1-108">[out] Puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugTypeEnum" che consente l'enumerazione di memorizzato nella cache gestite le rappresentazioni del [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi recuperato, in base agli identificatori di interfaccia in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="3fdd1-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fdd1-109">Note</span><span class="sxs-lookup"><span data-stu-id="3fdd1-109">Remarks</span></span>  
 <span data-ttu-id="3fdd1-110">Se il metodo non riesce a recuperare le informazioni per un identificatore di interfaccia specifica, la voce corrispondente nella raccolta "ICorDebugTypeEnum" verrà assegnato un tipo di `ELEMENT_TYPE_END` per gli errori a causa di problemi di recupero dei dati, o `ELEMENT_TYPE_VOID` per interfaccia sconosciuta identificatori.</span><span class="sxs-lookup"><span data-stu-id="3fdd1-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdd1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fdd1-111">Requirements</span></span>  
 <span data-ttu-id="3fdd1-112">**Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdd1-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="3fdd1-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3fdd1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fdd1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fdd1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fdd1-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdd1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdd1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fdd1-116">See Also</span></span>  
 [<span data-ttu-id="3fdd1-117">ICorDebugAppDomain3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3fdd1-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
