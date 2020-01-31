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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791265"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="3dc5f-102">Metodo ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="3dc5f-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="3dc5f-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il token di campo specificato nel stack frame specificato.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dc5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dc5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3dc5f-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="3dc5f-106">in Token `mdFieldDef` che specifica il campo statico.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="3dc5f-107">in Puntatore a un ICorDebugFrame che rappresenta l'stack frame.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3dc5f-108">out Puntatore all'indirizzo di un `ICorDebugValue` che contiene il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dc5f-109">Note</span><span class="sxs-lookup"><span data-stu-id="3dc5f-109">Remarks</span></span>  
 <span data-ttu-id="3dc5f-110">Il metodo `GetStaticFieldValue` può essere utilizzato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal metodo [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3dc5f-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="3dc5f-111">Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata di [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) sull'oggetto ICorDebugClass restituito da [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="3dc5f-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="3dc5f-112">Per i tipi generici, un valore di campo statico sarà relativo a una particolare creazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="3dc5f-113">Se, inoltre, il campo statico potrebbe essere relativo a un thread, a un contesto o a un dominio dell'applicazione, il stack frame consentirà al debugger di determinare il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dc5f-114">Note</span><span class="sxs-lookup"><span data-stu-id="3dc5f-114">Remarks</span></span>  
 <span data-ttu-id="3dc5f-115">`GetStaticFieldValue` può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="3dc5f-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dc5f-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3dc5f-116">Requirements</span></span>  
 <span data-ttu-id="3dc5f-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dc5f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dc5f-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dc5f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dc5f-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dc5f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dc5f-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc5f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
