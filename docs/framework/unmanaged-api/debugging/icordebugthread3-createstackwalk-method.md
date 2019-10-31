---
title: Metodo ICorDebugThread3::CreateStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: ca5db8c8570cedd9b0412b71058d453112a1831c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140123"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="dff81-102">Metodo ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="dff81-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="dff81-103">Crea un oggetto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) per il thread il cui stack si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="dff81-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dff81-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff81-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dff81-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="dff81-106">out Puntatore all'indirizzo dell'oggetto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) per il thread di cui si desidera rimuovere lo stack.</span><span class="sxs-lookup"><span data-stu-id="dff81-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dff81-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dff81-107">Return Value</span></span>  
 <span data-ttu-id="dff81-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="dff81-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dff81-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dff81-109">HRESULT</span></span>|<span data-ttu-id="dff81-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dff81-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dff81-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dff81-111">S_OK</span></span>|<span data-ttu-id="dff81-112">Creazione dell'oggetto `ICorDebugStackWalk` completata.</span><span class="sxs-lookup"><span data-stu-id="dff81-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="dff81-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dff81-113">E_FAIL</span></span>|<span data-ttu-id="dff81-114">L'oggetto `ICorDebugStackWalk` non è stato creato.</span><span class="sxs-lookup"><span data-stu-id="dff81-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="dff81-115">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="dff81-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dff81-116">Note</span><span class="sxs-lookup"><span data-stu-id="dff81-116">Remarks</span></span>  
 <span data-ttu-id="dff81-117">Se il metodo `CreateStackWalk` ha esito positivo, il contesto dell'oggetto `ICorDebugStackWalk` restituito viene impostato sul contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="dff81-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff81-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dff81-118">Requirements</span></span>  
 <span data-ttu-id="dff81-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff81-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff81-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dff81-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dff81-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dff81-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dff81-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff81-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff81-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dff81-123">See also</span></span>

- [<span data-ttu-id="dff81-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dff81-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dff81-125">Debug</span><span class="sxs-lookup"><span data-stu-id="dff81-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
