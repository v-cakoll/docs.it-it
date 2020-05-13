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
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213192"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="5983d-102">Metodo ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="5983d-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="5983d-103">Contrassegna la funzione rappresentata da questo ICorDebugFunction2 per Just My Code esecuzione di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="5983d-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5983d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5983d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5983d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5983d-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="5983d-106">in Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostare su `false` .</span><span class="sxs-lookup"><span data-stu-id="5983d-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="5983d-107">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="5983d-107">Return Values</span></span>  
  
|<span data-ttu-id="5983d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5983d-108">HRESULT</span></span>|<span data-ttu-id="5983d-109">Description</span><span class="sxs-lookup"><span data-stu-id="5983d-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5983d-110">La funzione è stata contrassegnata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5983d-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="5983d-111">Impossibile contrassegnare la funzione come codice utente perché non può essere sottoposta a debug.</span><span class="sxs-lookup"><span data-stu-id="5983d-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5983d-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5983d-112">Remarks</span></span>  
 <span data-ttu-id="5983d-113">Un Just My Code stepper ignorerà il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="5983d-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="5983d-114">Il codice utente deve essere un subset del codice di cui è possibile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="5983d-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5983d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5983d-115">Requirements</span></span>  
 <span data-ttu-id="5983d-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5983d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5983d-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5983d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5983d-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5983d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5983d-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5983d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
