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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0089502519a5a5530b7ed2a5896f7c445ccb128
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722642"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="01ea0-102">Metodo ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="01ea0-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="01ea0-103">Crea un' [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto per il thread la cui stack si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="01ea0-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01ea0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01ea0-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01ea0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01ea0-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="01ea0-106">[out] Puntatore all'indirizzo del [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto per il thread la cui stack si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="01ea0-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01ea0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01ea0-107">Return Value</span></span>  
 <span data-ttu-id="01ea0-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="01ea0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="01ea0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01ea0-109">HRESULT</span></span>|<span data-ttu-id="01ea0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01ea0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01ea0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01ea0-111">S_OK</span></span>|<span data-ttu-id="01ea0-112">Il `ICorDebugStackWalk` oggetto è stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="01ea0-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="01ea0-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01ea0-113">E_FAIL</span></span>|<span data-ttu-id="01ea0-114">Il `ICorDebugStackWalk` oggetto non è stato creato.</span><span class="sxs-lookup"><span data-stu-id="01ea0-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="01ea0-115">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="01ea0-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01ea0-116">Note</span><span class="sxs-lookup"><span data-stu-id="01ea0-116">Remarks</span></span>  
 <span data-ttu-id="01ea0-117">Se il `CreateStackWalk` metodo ha esito positivo, l'oggetto restituito `ICorDebugStackWalk` contesto dell'oggetto viene impostato il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="01ea0-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01ea0-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01ea0-118">Requirements</span></span>  
 <span data-ttu-id="01ea0-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01ea0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01ea0-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01ea0-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01ea0-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01ea0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01ea0-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01ea0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ea0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01ea0-123">See also</span></span>
- [<span data-ttu-id="01ea0-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="01ea0-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="01ea0-125">Debug</span><span class="sxs-lookup"><span data-stu-id="01ea0-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
