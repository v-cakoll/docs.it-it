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
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788670"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="80a37-102">Metodo ICorDebugExceptionObjectValue::EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="80a37-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="80a37-103">Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="80a37-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80a37-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80a37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80a37-105">Parameters</span></span>  
 <span data-ttu-id="80a37-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="80a37-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="80a37-107">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) che è un enumeratore di analisi dello stack per un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="80a37-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80a37-108">Note</span><span class="sxs-lookup"><span data-stu-id="80a37-108">Remarks</span></span>  
 <span data-ttu-id="80a37-109">Se non sono disponibili informazioni sullo stack di chiamate, il metodo restituisce `S_OK`e [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) è un enumeratore valido con lunghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="80a37-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="80a37-110">Se il metodo non è in grado di recuperare informazioni sulla traccia dello stack, il valore restituito è `E_FAIL` e non viene restituito alcun enumeratore.</span><span class="sxs-lookup"><span data-stu-id="80a37-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="80a37-111">L'oggetto [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) è responsabile della decodifica dei dati di traccia dello stack dal campo `_stackTrace` dell'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="80a37-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80a37-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="80a37-112">Requirements</span></span>  
 <span data-ttu-id="80a37-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80a37-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80a37-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80a37-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80a37-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80a37-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80a37-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80a37-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a37-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80a37-117">See also</span></span>

- [<span data-ttu-id="80a37-118">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="80a37-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="80a37-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="80a37-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
