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
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095126"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="7c179-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="7c179-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="7c179-103">Ottiene un enumeratore per memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi in un dominio dell'applicazione basati sui rispettivi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7c179-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c179-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c179-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c179-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c179-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="7c179-106">[in] Il numero di tipi richiesti.</span><span class="sxs-lookup"><span data-stu-id="7c179-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="7c179-107">[in] Un puntatore a una matrice contenente gli identificatori di interfaccia corrispondenti per le rappresentazioni di gestito il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="7c179-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="7c179-108">[out] Un puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugTypeEnum" che consente l'enumerazione di memorizzato nella cache gestita le rappresentazioni del [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi recuperati in base gli identificatori di interfaccia in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="7c179-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c179-109">Note</span><span class="sxs-lookup"><span data-stu-id="7c179-109">Remarks</span></span>  
 <span data-ttu-id="7c179-110">Se il metodo non riesce a recuperare le informazioni per un identificatore di interfaccia specifica, la voce corrispondente nella raccolta "ICorDebugTypeEnum" sarà un tipo `ELEMENT_TYPE_END` per gli errori a causa di problemi di recupero dei dati, o `ELEMENT_TYPE_VOID` per interfaccia sconosciuto identificatori.</span><span class="sxs-lookup"><span data-stu-id="7c179-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c179-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c179-111">Requirements</span></span>  
 **<span data-ttu-id="7c179-112">Piattaforme:</span><span class="sxs-lookup"><span data-stu-id="7c179-112">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="7c179-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c179-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c179-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c179-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7c179-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7c179-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c179-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c179-116">See also</span></span>

- [<span data-ttu-id="7c179-117">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="7c179-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
