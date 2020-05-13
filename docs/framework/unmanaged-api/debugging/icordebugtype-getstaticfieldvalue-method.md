---
title: Metodo ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 83ac91133b226e2ac263356941c3fc3288355e7e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379942"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="e5a5b-102">Metodo ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="e5a5b-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="e5a5b-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il token di campo specificato nel stack frame specificato.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5a5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5a5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5a5b-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="e5a5b-106">in `mdFieldDef`Token che specifica il campo statico.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="e5a5b-107">in Puntatore a un ICorDebugFrame che rappresenta l'stack frame.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e5a5b-108">out Puntatore all'indirizzo di un oggetto `ICorDebugValue` che contiene il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5a5b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5a5b-109">Remarks</span></span>  
 <span data-ttu-id="e5a5b-110">Il `GetStaticFieldValue` metodo può essere utilizzato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal metodo [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e5a5b-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="e5a5b-111">Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata di [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) sull'oggetto ICorDebugClass restituito da [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5a5b-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="e5a5b-112">Per i tipi generici, un valore di campo statico sarà relativo a una particolare creazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="e5a5b-113">Se, inoltre, il campo statico potrebbe essere relativo a un thread, a un contesto o a un dominio dell'applicazione, il stack frame consentirà al debugger di determinare il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5a5b-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5a5b-114">Remarks</span></span>  
 <span data-ttu-id="e5a5b-115">`GetStaticFieldValue`può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a5b-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5a5b-116">Requirements</span></span>  
 <span data-ttu-id="e5a5b-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a5b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a5b-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5a5b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5a5b-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a5b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a5b-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a5b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
