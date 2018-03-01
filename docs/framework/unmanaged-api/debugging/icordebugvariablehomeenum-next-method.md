---
title: Metodo ICorDebugVariableHomeEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3bab158cbbe2eaf6e52ae0df6a0eed86d3d0b8ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="72c79-102">Metodo ICorDebugVariableHomeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="72c79-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="72c79-103">Ottiene il numero specificato di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanze che contengono informazioni sulle variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="72c79-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72c79-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72c79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72c79-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="72c79-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="72c79-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="72c79-107">Matrice di puntatori, ognuno dei quali punta a un [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto che fornisce informazioni su una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="72c79-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="72c79-108">[out] Il numero di istanze effettivamente restituiti in oggetti.</span><span class="sxs-lookup"><span data-stu-id="72c79-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72c79-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72c79-109">Return Value</span></span>  
 <span data-ttu-id="72c79-110">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="72c79-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="72c79-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72c79-111">HRESULT</span></span>|<span data-ttu-id="72c79-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72c79-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="72c79-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="72c79-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="72c79-114">Recuperata il numero effettivo di istanze, come indicato in `pceltFetched`, è inferiore al numero di istanze richiesto.</span><span class="sxs-lookup"><span data-stu-id="72c79-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72c79-115">Note</span><span class="sxs-lookup"><span data-stu-id="72c79-115">Remarks</span></span>  
 <span data-ttu-id="72c79-116">Il [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) che consente di recuperare un massimo di `celt` gli oggetti a partire dalla posizione corrente dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="72c79-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="72c79-117">Quando termina, il metodo `pceltFetched` contiene il numero effettivo di oggetti recuperati.</span><span class="sxs-lookup"><span data-stu-id="72c79-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c79-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72c79-118">Requirements</span></span>  
 <span data-ttu-id="72c79-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c79-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c79-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="72c79-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72c79-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72c79-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72c79-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72c79-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c79-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72c79-123">See Also</span></span>  
 [<span data-ttu-id="72c79-124">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="72c79-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [<span data-ttu-id="72c79-125">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="72c79-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
