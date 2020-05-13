---
title: Metodo ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 7bf73266f0269cfcd5371c5155856800036cc066
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209838"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="8481c-102">Metodo ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="8481c-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="8481c-103">Ottiene la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="8481c-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8481c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8481c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8481c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8481c-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="8481c-106">out Puntatore all'indirizzo di un oggetto ICorDebugFunction che rappresenta la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="8481c-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8481c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8481c-107">Remarks</span></span>  
 <span data-ttu-id="8481c-108">Il `GetFunction` metodo può non riuscire se il frame non è associato ad alcuna funzione particolare.</span><span class="sxs-lookup"><span data-stu-id="8481c-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8481c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8481c-109">Requirements</span></span>  
 <span data-ttu-id="8481c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8481c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8481c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8481c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8481c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8481c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8481c-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8481c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
