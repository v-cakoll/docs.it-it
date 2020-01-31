---
title: 'Metodo metodo icordebugtype2:: GetTypeID'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791233"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="6510f-102">Metodo metodo icordebugtype2:: GetTypeID</span><span class="sxs-lookup"><span data-stu-id="6510f-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="6510f-103">Ottiene un [COR_TYPEID](cor-typeid-structure.md) per questo tipo.</span><span class="sxs-lookup"><span data-stu-id="6510f-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6510f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6510f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6510f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6510f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6510f-106">out Puntatore al [COR_TYPEID](cor-typeid-structure.md) per questo ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="6510f-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6510f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6510f-107">Return Value</span></span>  
 <span data-ttu-id="6510f-108">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6510f-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="6510f-109">I codici `HRESULT` includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6510f-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="6510f-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="6510f-110">Return code</span></span>|<span data-ttu-id="6510f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6510f-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="6510f-112">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="6510f-112">Method succeeded.</span></span> <span data-ttu-id="6510f-113">Il metodo ha recuperato un [COR_TYPEID](cor-typeid-structure.md)valido.</span><span class="sxs-lookup"><span data-stu-id="6510f-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="6510f-114">Il tipo non è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="6510f-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="6510f-115">Il tipo non è supportato.</span><span class="sxs-lookup"><span data-stu-id="6510f-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6510f-116">Note</span><span class="sxs-lookup"><span data-stu-id="6510f-116">Remarks</span></span>  
 <span data-ttu-id="6510f-117">Questo metodo fornisce un mapping da ICorDebugType, che rappresenta un tipo che può essere caricato o meno nel runtime, in una [COR_TYPEID](cor-typeid-structure.md), che funge da handle opaco che identifica un tipo caricato nel Runtime.</span><span class="sxs-lookup"><span data-stu-id="6510f-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="6510f-118">Quando il tipo rappresentato da ICorDebugType non è ancora stato caricato, questo metodo restituisce `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="6510f-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="6510f-119">Se il tipo non è supportato, restituisce `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="6510f-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6510f-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6510f-120">Requirements</span></span>  
 <span data-ttu-id="6510f-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6510f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6510f-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6510f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6510f-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6510f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6510f-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6510f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6510f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6510f-125">See also</span></span>

- [<span data-ttu-id="6510f-126">Interfaccia ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="6510f-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)
