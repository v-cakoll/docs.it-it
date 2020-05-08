---
title: Metodo ICorDebugEval::CreateValue
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976252"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="0eff8-102">Metodo ICorDebugEval::CreateValue</span><span class="sxs-lookup"><span data-stu-id="0eff8-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="0eff8-103">Crea un valore del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="0eff8-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="0eff8-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="0eff8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0eff8-105">Usare invece [ICorDebugEval2:: CreateValueForType](icordebugeval2-createvaluefortype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff8-105">Use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eff8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0eff8-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eff8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0eff8-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="0eff8-108">in Valore dell'enumerazione [CorElementType](../metadata/corelementtype-enumeration.md) che specifica il tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="0eff8-108">[in] A value of the [CorElementType](../metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="0eff8-109">in Puntatore a un oggetto [ICorDebugClass](icordebugclass-interface.md) che specifica la classe del valore, se il tipo non è un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="0eff8-109">[in] Pointer to an [ICorDebugClass](icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0eff8-110">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="0eff8-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eff8-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0eff8-111">Remarks</span></span>  
 <span data-ttu-id="0eff8-112">`CreateValue`Crea un `ICorDebugValue` oggetto del tipo specificato per l'utilizzo esclusivo in una valutazione di funzione.</span><span class="sxs-lookup"><span data-stu-id="0eff8-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="0eff8-113">Questo oggetto valore può essere utilizzato per passare le costanti utente come parametri.</span><span class="sxs-lookup"><span data-stu-id="0eff8-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="0eff8-114">Se il tipo del valore è un tipo primitivo, il valore iniziale è zero o null.</span><span class="sxs-lookup"><span data-stu-id="0eff8-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="0eff8-115">Usare [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) per impostare il valore di un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="0eff8-115">Use [ICorDebugGenericValue::SetValue](icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="0eff8-116">Se il valore di `elementType` è ELEMENT_TYPE_CLASS, viene visualizzato un valore "ICorDebugReferenceValue" (restituito `ppValue`in) che rappresenta il riferimento all'oggetto null.</span><span class="sxs-lookup"><span data-stu-id="0eff8-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="0eff8-117">È possibile utilizzare questo oggetto per passare valori null a una valutazione di funzione con parametri di riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0eff8-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="0eff8-118">Non è possibile impostare `ICorDebugValue` su nulla; rimane sempre null.</span><span class="sxs-lookup"><span data-stu-id="0eff8-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eff8-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0eff8-119">Requirements</span></span>  
 <span data-ttu-id="0eff8-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eff8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eff8-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eff8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eff8-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eff8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eff8-123">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="0eff8-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eff8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eff8-124">See also</span></span>

- [<span data-ttu-id="0eff8-125">Metodo CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="0eff8-125">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="0eff8-126">Interfaccia ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="0eff8-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
