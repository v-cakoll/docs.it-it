---
title: Metodo ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7649d91ca2b654952d1d5ab0d45f7903d3c46a32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745549"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="8f629-102">Metodo ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="8f629-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="8f629-103">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="8f629-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f629-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f629-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f629-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f629-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="8f629-106">[in] Un campo `Def` token che fa riferimento al campo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="8f629-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="8f629-107">[in] Un puntatore a un oggetto ICorDebugFrame che rappresenta la cornice per essere usato per distinguere tra thread, al contesto o campi statici relativi al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f629-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="8f629-108">Se il campo statico è rispetto a un thread, un contesto o un dominio dell'applicazione, il frame determinerà il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="8f629-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8f629-109">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="8f629-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f629-110">Note</span><span class="sxs-lookup"><span data-stu-id="8f629-110">Remarks</span></span>  
 <span data-ttu-id="8f629-111">Per i tipi con parametri, il valore di un campo statico è relativo alla creazione di un'istanza particolare.</span><span class="sxs-lookup"><span data-stu-id="8f629-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="8f629-112">Pertanto, se il costruttore della classe accetta i parametri di tipo <xref:System.Type>, chiamare [GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) invece di `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="8f629-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f629-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f629-113">Requirements</span></span>  
 <span data-ttu-id="8f629-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f629-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f629-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f629-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f629-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f629-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f629-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f629-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
