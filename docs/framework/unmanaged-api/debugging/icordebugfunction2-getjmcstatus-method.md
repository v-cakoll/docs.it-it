---
title: Metodo ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf0ba3938568524479e12b93ae8cebbcf52f909
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411729"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="cdcdf-102">Metodo ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="cdcdf-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="cdcdf-103">Ottiene un valore che indica se la funzione che è rappresentata dall'oggetto ICorDebugFunction2 è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="cdcdf-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdcdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdcdf-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdcdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cdcdf-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="cdcdf-106">[out] Un puntatore a un valore booleano che è `true`, se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false`.</span><span class="sxs-lookup"><span data-stu-id="cdcdf-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdcdf-107">Note</span><span class="sxs-lookup"><span data-stu-id="cdcdf-107">Remarks</span></span>  
 <span data-ttu-id="cdcdf-108">Se la funzione è rappresentato da questo `ICorDebugFunction2` Impossibile eseguire il debug, `pbIsJustMyCode` sarà sempre `false`.</span><span class="sxs-lookup"><span data-stu-id="cdcdf-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdcdf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdcdf-109">Requirements</span></span>  
 <span data-ttu-id="cdcdf-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdcdf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdcdf-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cdcdf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdcdf-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cdcdf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdcdf-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdcdf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
