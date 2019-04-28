---
title: Metodo ICorDebugVariableHomeEnum::Next
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be1ba87ae979911dd21647569725eafa2c80ffa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768810"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="7d219-102">Metodo ICorDebugVariableHomeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="7d219-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="7d219-103">Ottiene il numero specificato di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanze che contengono informazioni sulle variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="7d219-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d219-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d219-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d219-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d219-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7d219-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="7d219-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="7d219-107">Una matrice di puntatori, ognuno dei quali punta a un [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto che fornisce informazioni su un argomento di una funzione o variabile locale.</span><span class="sxs-lookup"><span data-stu-id="7d219-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7d219-108">[out] Il numero di istanze effettivamente restituiti in oggetti.</span><span class="sxs-lookup"><span data-stu-id="7d219-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d219-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7d219-109">Return Value</span></span>  
 <span data-ttu-id="7d219-110">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="7d219-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="7d219-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d219-111">HRESULT</span></span>|<span data-ttu-id="7d219-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d219-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7d219-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7d219-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7d219-114">Recuperato il numero effettivo di istanze, come riportati nelle `pceltFetched`, è inferiore al numero di istanze richieste.</span><span class="sxs-lookup"><span data-stu-id="7d219-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d219-115">Note</span><span class="sxs-lookup"><span data-stu-id="7d219-115">Remarks</span></span>  
 <span data-ttu-id="7d219-116">Il [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) che consente di recuperare un massimo di `celt` oggetti partendo dalla posizione corrente dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="7d219-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="7d219-117">Quando termina, il metodo `pceltFetched` contiene il numero effettivo di oggetti recuperati.</span><span class="sxs-lookup"><span data-stu-id="7d219-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d219-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d219-118">Requirements</span></span>  
 <span data-ttu-id="7d219-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d219-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d219-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d219-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d219-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d219-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d219-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d219-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d219-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d219-123">See also</span></span>

- [<span data-ttu-id="7d219-124">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="7d219-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="7d219-125">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="7d219-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
