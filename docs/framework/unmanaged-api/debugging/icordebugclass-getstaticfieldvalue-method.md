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
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471628"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="5b8e0-102">Metodo ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="5b8e0-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="5b8e0-103">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b8e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b8e0-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b8e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b8e0-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="5b8e0-106">[in] Un campo `Def` token che fa riferimento al campo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="5b8e0-107">[in] Un puntatore a un oggetto ICorDebugFrame che rappresenta la cornice per essere usato per distinguere tra thread, al contesto o campi statici relativi al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="5b8e0-108">Se il campo statico è rispetto a un thread, un contesto o un dominio dell'applicazione, il frame determinerà il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5b8e0-109">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b8e0-110">Note</span><span class="sxs-lookup"><span data-stu-id="5b8e0-110">Remarks</span></span>  
 <span data-ttu-id="5b8e0-111">Per i tipi con parametri, il valore di un campo statico è relativo alla creazione di un'istanza particolare.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="5b8e0-112">Pertanto, se il costruttore della classe accetta i parametri di tipo <xref:System.Type>, chiamare [GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) invece di `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="5b8e0-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b8e0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b8e0-113">Requirements</span></span>  
 <span data-ttu-id="5b8e0-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b8e0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b8e0-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b8e0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b8e0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b8e0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b8e0-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b8e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
