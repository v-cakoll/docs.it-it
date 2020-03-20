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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179066"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="da551-102">Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="da551-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="da551-103">Ottiene un enumeratore per i tipi di Windows Runtime memorizzati nella cache in un dominio applicazione in base ai relativi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="da551-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da551-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da551-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da551-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da551-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="da551-106">[in] Numero di tipi richiesti.</span><span class="sxs-lookup"><span data-stu-id="da551-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="da551-107">[in] Puntatore a una matrice che contiene gli identificatori di interfaccia corrispondenti alle rappresentazioni gestite dei tipi di Windows Runtime da recuperare.</span><span class="sxs-lookup"><span data-stu-id="da551-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="da551-108">[fuori] Puntatore all'indirizzo di un oggetto interfaccia "ICorDebugTypeEnum" che consente l'enumerazione delle rappresentazioni gestite `iidsToResolve`memorizzate nella cache dei tipi di Windows Runtime recuperati, in base agli identificatori di interfaccia in .</span><span class="sxs-lookup"><span data-stu-id="da551-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da551-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="da551-109">Remarks</span></span>  
 <span data-ttu-id="da551-110">Se il metodo non riesce a recuperare informazioni per un identificatore di interfaccia specifico, la `ELEMENT_TYPE_END` voce corrispondente nella raccolta "ICorDebugTypeEnum" avrà un tipo di per gli errori a causa di problemi di recupero dati o `ELEMENT_TYPE_VOID` per gli identificatori di interfaccia sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="da551-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da551-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da551-111">Requirements</span></span>  
 <span data-ttu-id="da551-112">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="da551-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="da551-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da551-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da551-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da551-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da551-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da551-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da551-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da551-116">See also</span></span>

- [<span data-ttu-id="da551-117">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="da551-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
