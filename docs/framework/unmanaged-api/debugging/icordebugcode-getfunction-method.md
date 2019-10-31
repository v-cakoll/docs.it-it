---
title: Metodo ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 217ca0a850926e5f697340cece264c6ed442a9bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125637"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="908cb-102">Metodo ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="908cb-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="908cb-103">Ottiene l'oggetto "ICorDebugFunction" associato a questo "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="908cb-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="908cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="908cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="908cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="908cb-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="908cb-106">out Puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="908cb-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="908cb-107">Note</span><span class="sxs-lookup"><span data-stu-id="908cb-107">Remarks</span></span>  
 <span data-ttu-id="908cb-108">`ICorDebugCode` e `ICorDebugFunction` mantenere una relazione uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="908cb-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="908cb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="908cb-109">Requirements</span></span>  
 <span data-ttu-id="908cb-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="908cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="908cb-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="908cb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="908cb-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="908cb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="908cb-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="908cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
