---
title: Metodo ICorDebugType2::GetTypeID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugType2.GetTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30b5259bfd39ac0c8c8b717d59a8d3165f6b6cbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="26c61-102">Metodo ICorDebugType2::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="26c61-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="26c61-103">Ottiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) per questo tipo.</span><span class="sxs-lookup"><span data-stu-id="26c61-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26c61-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26c61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26c61-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="26c61-106">[out] Un puntatore al [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) per ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="26c61-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26c61-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26c61-107">Return Value</span></span>  
 <span data-ttu-id="26c61-108">Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="26c61-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="26c61-109">Il `HRESULT` codici includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26c61-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="26c61-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="26c61-110">Return code</span></span>|<span data-ttu-id="26c61-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26c61-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="26c61-112">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="26c61-112">Method succeeded.</span></span> <span data-ttu-id="26c61-113">Il metodo ha recuperato un valore valido [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span><span class="sxs-lookup"><span data-stu-id="26c61-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="26c61-114">Il tipo non è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="26c61-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="26c61-115">Il tipo non è supportato.</span><span class="sxs-lookup"><span data-stu-id="26c61-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26c61-116">Note</span><span class="sxs-lookup"><span data-stu-id="26c61-116">Remarks</span></span>  
 <span data-ttu-id="26c61-117">Questo metodo fornisce un mapping dal ICorDebugType, che rappresenta un tipo che potrebbe non sono stato caricato in fase di esecuzione, a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), che funge da opaco gestiscono che identifica un tipo caricato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="26c61-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="26c61-118">Quando il tipo che rappresenta il ICorDebugType non è stato ancora stato caricato, questo metodo restituisce `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="26c61-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="26c61-119">Se il tipo non è supportato, restituisce `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="26c61-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c61-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26c61-120">Requirements</span></span>  
 <span data-ttu-id="26c61-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26c61-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c61-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="26c61-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26c61-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26c61-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26c61-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c61-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c61-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c61-125">See Also</span></span>  
 [<span data-ttu-id="26c61-126">Interfaccia ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="26c61-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
