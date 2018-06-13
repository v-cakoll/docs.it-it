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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d67784daee055106f104d74d098b9926c6de2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417112"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="57e78-102">Metodo ICorDebugEval::CreateValue</span><span class="sxs-lookup"><span data-stu-id="57e78-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="57e78-103">Crea un valore del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="57e78-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="57e78-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="57e78-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="57e78-105">Utilizzare [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="57e78-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57e78-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57e78-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57e78-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="57e78-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="57e78-108">[in] Il valore di [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumerazione che specifica il tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="57e78-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="57e78-109">[in] Puntatore a un [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) oggetto che specifica la classe di valore, se il tipo non è un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="57e78-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="57e78-110">[out] Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="57e78-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57e78-111">Note</span><span class="sxs-lookup"><span data-stu-id="57e78-111">Remarks</span></span>  
 <span data-ttu-id="57e78-112">`CreateValue` Crea un `ICorDebugValue` oggetto del tipo specificato al solo scopo di utilizzo in una valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="57e78-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="57e78-113">Questo oggetto valore utilizzabile per passare le costanti utente come parametri.</span><span class="sxs-lookup"><span data-stu-id="57e78-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="57e78-114">Se il tipo del valore è un tipo primitivo, il valore iniziale è zero o null.</span><span class="sxs-lookup"><span data-stu-id="57e78-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="57e78-115">Utilizzare [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) per impostare il valore di un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="57e78-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="57e78-116">Se il valore di `elementType` è ELEMENT_TYPE_CLASS, si ottiene un'interfaccia "ICorDebugReferenceValue" (restituiti in `ppValue`) che rappresenta il riferimento di oggetto null.</span><span class="sxs-lookup"><span data-stu-id="57e78-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="57e78-117">Passare null per una valutazione della funzione che dispone di parametri di riferimento di oggetto, è possibile utilizzare questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="57e78-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="57e78-118">Non è possibile impostare il `ICorDebugValue` effettuare alcuna azione; rimane sempre null.</span><span class="sxs-lookup"><span data-stu-id="57e78-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57e78-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57e78-119">Requirements</span></span>  
 <span data-ttu-id="57e78-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57e78-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57e78-121">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="57e78-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57e78-122">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="57e78-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57e78-123">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="57e78-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57e78-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57e78-124">See Also</span></span>  
    
 [<span data-ttu-id="57e78-125">Metodo CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="57e78-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 <span data-ttu-id="57e78-126">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="57e78-126">ICorDebugValue</span></span>
