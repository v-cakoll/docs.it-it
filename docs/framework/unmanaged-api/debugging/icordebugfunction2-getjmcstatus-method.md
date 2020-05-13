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
ms.openlocfilehash: 56dc5f87b32b3aaa0bfbb69541d5a01ae26606ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213234"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="37567-102">Metodo ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="37567-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="37567-103">Ottiene un valore che indica se la funzione rappresentata da questo oggetto ICorDebugFunction2 è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="37567-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37567-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37567-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37567-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37567-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="37567-106">out Puntatore a un valore booleano `true` , se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false` .</span><span class="sxs-lookup"><span data-stu-id="37567-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37567-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="37567-107">Remarks</span></span>  
 <span data-ttu-id="37567-108">Se la funzione rappresentata da questo oggetto `ICorDebugFunction2` non può essere `pbIsJustMyCode` sottoposta a debug, sarà sempre `false` .</span><span class="sxs-lookup"><span data-stu-id="37567-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37567-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37567-109">Requirements</span></span>  
 <span data-ttu-id="37567-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37567-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37567-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37567-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37567-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37567-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37567-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37567-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
