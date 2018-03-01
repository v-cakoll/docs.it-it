---
title: Metodo ICorDebugThread3::CreateStackWalk
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3b587a69c7acc3115c282eac065d304dc892b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="c05ef-102">Metodo ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="c05ef-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="c05ef-103">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto per il thread il cui stack si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c05ef-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c05ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c05ef-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c05ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c05ef-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="c05ef-106">[out] Puntatore all'indirizzo del [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto per il thread il cui stack si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c05ef-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c05ef-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c05ef-107">Return Value</span></span>  
 <span data-ttu-id="c05ef-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="c05ef-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c05ef-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c05ef-109">HRESULT</span></span>|<span data-ttu-id="c05ef-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c05ef-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c05ef-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c05ef-111">S_OK</span></span>|<span data-ttu-id="c05ef-112">Il `ICorDebugStackWalk` oggetto è stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c05ef-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="c05ef-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c05ef-113">E_FAIL</span></span>|<span data-ttu-id="c05ef-114">Il `ICorDebugStackWalk` non è stato creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c05ef-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c05ef-115">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="c05ef-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c05ef-116">Note</span><span class="sxs-lookup"><span data-stu-id="c05ef-116">Remarks</span></span>  
 <span data-ttu-id="c05ef-117">Se il `CreateStackWalk` metodo ha esito positivo, l'oggetto restituito `ICorDebugStackWalk` contesto dell'oggetto viene impostato il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="c05ef-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c05ef-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c05ef-118">Requirements</span></span>  
 <span data-ttu-id="c05ef-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c05ef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c05ef-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c05ef-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c05ef-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c05ef-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c05ef-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c05ef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05ef-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c05ef-123">See Also</span></span>  
 [<span data-ttu-id="c05ef-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c05ef-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c05ef-125">Debug</span><span class="sxs-lookup"><span data-stu-id="c05ef-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
