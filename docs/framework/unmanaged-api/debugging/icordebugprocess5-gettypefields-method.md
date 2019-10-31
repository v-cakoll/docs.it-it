---
title: Metodo ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132664"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="698da-102">Metodo ICorDebugProcess5::GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="698da-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="698da-103">Fornisce informazioni sui campi che appartengono a un tipo.</span><span class="sxs-lookup"><span data-stu-id="698da-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="698da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="698da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="698da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="698da-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="698da-106">in Identificatore del tipo le cui informazioni sul campo vengono recuperate.</span><span class="sxs-lookup"><span data-stu-id="698da-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="698da-107">in Numero di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) di cui è necessario recuperare le informazioni sul campo.</span><span class="sxs-lookup"><span data-stu-id="698da-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="698da-108">out Matrice di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) che forniscono informazioni sui campi che appartengono al tipo.</span><span class="sxs-lookup"><span data-stu-id="698da-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="698da-109">out Puntatore al numero di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) inclusi nel `fields`.</span><span class="sxs-lookup"><span data-stu-id="698da-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="698da-110">Note</span><span class="sxs-lookup"><span data-stu-id="698da-110">Remarks</span></span>  
 <span data-ttu-id="698da-111">Il parametro `celt`, che specifica il numero di campi le cui informazioni sul campo utilizzate dal metodo per popolare `fields`, devono corrispondere al valore del campo `COR_TYPE_LAYOUT::numFields`.</span><span class="sxs-lookup"><span data-stu-id="698da-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="698da-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="698da-112">Requirements</span></span>  
 <span data-ttu-id="698da-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="698da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="698da-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="698da-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="698da-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="698da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="698da-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="698da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698da-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="698da-117">See also</span></span>

- [<span data-ttu-id="698da-118">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="698da-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="698da-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="698da-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
