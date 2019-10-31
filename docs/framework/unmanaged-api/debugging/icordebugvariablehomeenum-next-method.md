---
title: 'ICorDebugVariableHomeEnum:: Next (metodo)'
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
ms.openlocfilehash: 9c2c16789fb61099c9b7c58154810739d225af1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121926"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="6d98a-102">ICorDebugVariableHomeEnum:: Next (metodo)</span><span class="sxs-lookup"><span data-stu-id="6d98a-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="6d98a-103">Ottiene il numero specificato di istanze di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="6d98a-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d98a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d98a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d98a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d98a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6d98a-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="6d98a-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="6d98a-107">Matrice di puntatori, ciascuno dei quali punta a un oggetto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) che fornisce informazioni su una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="6d98a-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6d98a-108">out Numero di istanze effettivamente restituite negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6d98a-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d98a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6d98a-109">Return Value</span></span>  
 <span data-ttu-id="6d98a-110">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d98a-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="6d98a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d98a-111">HRESULT</span></span>|<span data-ttu-id="6d98a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d98a-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6d98a-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6d98a-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6d98a-114">Il numero effettivo di istanze recuperate, come riflesso in `pceltFetched`, è inferiore al numero di istanze richieste.</span><span class="sxs-lookup"><span data-stu-id="6d98a-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d98a-115">Note</span><span class="sxs-lookup"><span data-stu-id="6d98a-115">Remarks</span></span>  
 <span data-ttu-id="6d98a-116">Il metodo [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) recupera un massimo di `celt` oggetti a partire dalla posizione corrente dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="6d98a-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="6d98a-117">Quando il metodo restituisce un risultato, `pceltFetched` contiene il numero effettivo di oggetti recuperati.</span><span class="sxs-lookup"><span data-stu-id="6d98a-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d98a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d98a-118">Requirements</span></span>  
 <span data-ttu-id="6d98a-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d98a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d98a-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d98a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d98a-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d98a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d98a-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d98a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d98a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d98a-123">See also</span></span>

- [<span data-ttu-id="6d98a-124">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="6d98a-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="6d98a-125">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="6d98a-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
