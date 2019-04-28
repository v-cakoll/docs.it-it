---
title: Metodo ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49ced1b4be888c7550c3927d1b319ab2f0bef086
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763776"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="77dd9-102">Metodo ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="77dd9-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="77dd9-103">Contrassegna la funzione rappresentata da ICorDebugFunction2 per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="77dd9-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77dd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77dd9-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77dd9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77dd9-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="77dd9-106">[in] Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="77dd9-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="77dd9-107">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="77dd9-107">Return Values</span></span>  
  
|<span data-ttu-id="77dd9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77dd9-108">HRESULT</span></span>|<span data-ttu-id="77dd9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77dd9-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="77dd9-110">La funzione è stata contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="77dd9-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="77dd9-111">La funzione non può essere contrassegnata come codice utente perché non è possibile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="77dd9-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77dd9-112">Note</span><span class="sxs-lookup"><span data-stu-id="77dd9-112">Remarks</span></span>  
 <span data-ttu-id="77dd9-113">Un Just My Code ignorerà il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="77dd9-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="77dd9-114">Il codice utente deve essere un subset di debug.</span><span class="sxs-lookup"><span data-stu-id="77dd9-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77dd9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77dd9-115">Requirements</span></span>  
 <span data-ttu-id="77dd9-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77dd9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77dd9-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77dd9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77dd9-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77dd9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77dd9-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77dd9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
