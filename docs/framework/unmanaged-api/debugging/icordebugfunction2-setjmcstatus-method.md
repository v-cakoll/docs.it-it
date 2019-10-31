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
ms.openlocfilehash: 758364b2d63343e464b727d5a1c1817533a6acea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137789"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="13df7-102">Metodo ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="13df7-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="13df7-103">Contrassegna la funzione rappresentata da questo ICorDebugFunction2 per Just My Code esecuzione di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="13df7-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13df7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13df7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13df7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13df7-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="13df7-106">in Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostare su `false`.</span><span class="sxs-lookup"><span data-stu-id="13df7-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="13df7-107">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="13df7-107">Return Values</span></span>  
  
|<span data-ttu-id="13df7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13df7-108">HRESULT</span></span>|<span data-ttu-id="13df7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13df7-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="13df7-110">La funzione è stata contrassegnata correttamente.</span><span class="sxs-lookup"><span data-stu-id="13df7-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="13df7-111">Impossibile contrassegnare la funzione come codice utente perché non può essere sottoposta a debug.</span><span class="sxs-lookup"><span data-stu-id="13df7-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13df7-112">Note</span><span class="sxs-lookup"><span data-stu-id="13df7-112">Remarks</span></span>  
 <span data-ttu-id="13df7-113">Un Just My Code stepper ignorerà il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="13df7-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="13df7-114">Il codice utente deve essere un subset del codice di cui è possibile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="13df7-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13df7-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13df7-115">Requirements</span></span>  
 <span data-ttu-id="13df7-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13df7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13df7-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13df7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13df7-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13df7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13df7-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13df7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
