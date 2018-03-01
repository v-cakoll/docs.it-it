---
title: Metodo ICorDebugClass::GetStaticFieldValue
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21176eb73b3655fe8bd4b2187b6da49a3c31bd82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="25503-102">Metodo ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="25503-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="25503-103">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="25503-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25503-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25503-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25503-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25503-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="25503-106">[in] Un campo `Def` token che fa riferimento il campo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="25503-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="25503-107">[in] Puntatore a un oggetto ICorDebugFrame che rappresenta il frame da utilizzare per distinguere tra i thread, di contesto o campi statici relativi al dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="25503-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="25503-108">Se il campo statico è relativo a un thread, un contesto o dominio applicazione, il frame determina il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="25503-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="25503-109">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="25503-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25503-110">Note</span><span class="sxs-lookup"><span data-stu-id="25503-110">Remarks</span></span>  
 <span data-ttu-id="25503-111">Per i tipi con parametri, il valore di un campo statico è rispetto alla creazione di un'istanza particolare.</span><span class="sxs-lookup"><span data-stu-id="25503-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="25503-112">Pertanto, se il costruttore della classe accetta parametri di tipo <xref:System.Type>, chiamare [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) anziché `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="25503-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25503-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25503-113">Requirements</span></span>  
 <span data-ttu-id="25503-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25503-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25503-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="25503-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25503-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25503-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25503-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25503-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
