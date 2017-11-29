---
title: Metodo ICorDebugFunction2::SetJMCStatus
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="780a1-102">Metodo ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="780a1-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="780a1-103">Contrassegna la funzione rappresentata da ICorDebugFunction2 per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="780a1-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="780a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="780a1-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="780a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="780a1-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="780a1-106">[in] Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="780a1-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="780a1-107">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="780a1-107">Return Values</span></span>  
  
|<span data-ttu-id="780a1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="780a1-108">HRESULT</span></span>|<span data-ttu-id="780a1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="780a1-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="780a1-110">La funzione è stata contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="780a1-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="780a1-111">Impossibile contrassegnare la funzione come codice utente perché è Impossibile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="780a1-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="780a1-112">Note</span><span class="sxs-lookup"><span data-stu-id="780a1-112">Remarks</span></span>  
 <span data-ttu-id="780a1-113">Un Just My Code ignorerà il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="780a1-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="780a1-114">Il codice utente deve essere un subset di debug.</span><span class="sxs-lookup"><span data-stu-id="780a1-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780a1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="780a1-115">Requirements</span></span>  
 <span data-ttu-id="780a1-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="780a1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780a1-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="780a1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="780a1-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="780a1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="780a1-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780a1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
