---
title: Metodo ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09f1bc2ae9d56eeb6a6242c32d14bf950684d69d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415613"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="30da5-102">Metodo ICorDebugExceptionObjectValue::EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="30da5-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="30da5-103">Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="30da5-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30da5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30da5-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30da5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30da5-105">Parameters</span></span>  
 <span data-ttu-id="30da5-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="30da5-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="30da5-107">[out] Un puntatore all'indirizzo di un [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) oggetto dell'interfaccia che è un enumeratore di traccia dello stack per un oggetto eccezione gestito.</span><span class="sxs-lookup"><span data-stu-id="30da5-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30da5-108">Note</span><span class="sxs-lookup"><span data-stu-id="30da5-108">Remarks</span></span>  
 <span data-ttu-id="30da5-109">Se non è disponibile alcuna informazione di stack di chiamate, il metodo restituisce `S_OK`, e [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) è un enumeratore valido con una lunghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="30da5-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="30da5-110">Se il metodo è riuscito a recuperare le informazioni di traccia di stack, il valore restituito è `E_FAIL` e non viene restituito alcun enumeratore.</span><span class="sxs-lookup"><span data-stu-id="30da5-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="30da5-111">Il [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) oggetto è responsabile per la decodifica di dati di traccia dello stack di `_stackTrace` campo dell'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="30da5-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30da5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30da5-112">Requirements</span></span>  
 <span data-ttu-id="30da5-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30da5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30da5-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="30da5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30da5-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="30da5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30da5-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30da5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30da5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30da5-117">See Also</span></span>  
 [<span data-ttu-id="30da5-118">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="30da5-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="30da5-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30da5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
