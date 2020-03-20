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
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178597"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="9cabb-102">Metodo ICorDebugProcess5::GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="9cabb-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="9cabb-103">Fornisce informazioni sui campi che appartengono a un tipo.</span><span class="sxs-lookup"><span data-stu-id="9cabb-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cabb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cabb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cabb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cabb-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="9cabb-106">[in] Identificatore del tipo di cui vengono recuperate le informazioni sul campo.</span><span class="sxs-lookup"><span data-stu-id="9cabb-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="9cabb-107">[in] Numero di [COR_FIELD](cor-field-structure.md) oggetti di cui devono essere recuperate le informazioni sul campo.</span><span class="sxs-lookup"><span data-stu-id="9cabb-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="9cabb-108">[fuori] Matrice di [oggetti COR_FIELD](cor-field-structure.md) che forniscono informazioni sui campi che appartengono al tipo.</span><span class="sxs-lookup"><span data-stu-id="9cabb-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="9cabb-109">[fuori] Puntatore al numero di oggetti `fields` [COR_FIELD](cor-field-structure.md) inclusi in .</span><span class="sxs-lookup"><span data-stu-id="9cabb-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cabb-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9cabb-110">Remarks</span></span>  
 <span data-ttu-id="9cabb-111">Il `celt` parametro , che specifica il numero di campi `fields`le cui informazioni sul `COR_TYPE_LAYOUT::numFields` campo utilizza il metodo per popolare , devono corrispondere al valore del campo.</span><span class="sxs-lookup"><span data-stu-id="9cabb-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cabb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cabb-112">Requirements</span></span>  
 <span data-ttu-id="9cabb-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cabb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cabb-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cabb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cabb-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cabb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cabb-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cabb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cabb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cabb-117">See also</span></span>

- [<span data-ttu-id="9cabb-118">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="9cabb-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="9cabb-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9cabb-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
