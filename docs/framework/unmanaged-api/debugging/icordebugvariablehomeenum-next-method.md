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
ms.openlocfilehash: 980f563d3b11fbfcce48b6d7c05275af520e14f1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396497"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="95884-102">ICorDebugVariableHomeEnum:: Next (metodo)</span><span class="sxs-lookup"><span data-stu-id="95884-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="95884-103">Ottiene il numero specificato di istanze di [ICorDebugVariableHome](icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="95884-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95884-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95884-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95884-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95884-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="95884-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="95884-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="95884-107">Matrice di puntatori, ciascuno dei quali punta a un oggetto [ICorDebugVariableHome](icordebugvariablehome-interface.md) che fornisce informazioni su una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="95884-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="95884-108">out Numero di istanze effettivamente restituite negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="95884-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95884-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="95884-109">Return Value</span></span>  
 <span data-ttu-id="95884-110">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="95884-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="95884-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95884-111">HRESULT</span></span>|<span data-ttu-id="95884-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95884-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="95884-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="95884-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="95884-114">Il numero effettivo di istanze recuperate, come riflesso in `pceltFetched` , è inferiore al numero di istanze richieste.</span><span class="sxs-lookup"><span data-stu-id="95884-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95884-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="95884-115">Remarks</span></span>  
 <span data-ttu-id="95884-116">Il metodo [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un massimo di `celt` oggetti a partire dalla posizione corrente dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="95884-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="95884-117">Quando il metodo viene restituito, `pceltFetched` contiene il numero effettivo di oggetti recuperati.</span><span class="sxs-lookup"><span data-stu-id="95884-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95884-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95884-118">Requirements</span></span>  
 <span data-ttu-id="95884-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95884-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95884-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95884-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95884-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95884-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95884-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95884-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95884-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="95884-123">See also</span></span>

- [<span data-ttu-id="95884-124">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="95884-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="95884-125">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="95884-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
