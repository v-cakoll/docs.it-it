---
title: Metodo ICorProfilerFunctionEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: 0f096f76ec47cfe3399e9184eb82bf20040efbbb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503042"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="eede9-102">Metodo ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="eede9-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="eede9-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="eede9-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eede9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eede9-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eede9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eede9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="eede9-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="eede9-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eede9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eede9-107">Return Value</span></span>  
 <span data-ttu-id="eede9-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="eede9-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eede9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eede9-109">HRESULT</span></span>|<span data-ttu-id="eede9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eede9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eede9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eede9-111">S_OK</span></span>|<span data-ttu-id="eede9-112">`celt`gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="eede9-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="eede9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eede9-113">S_FALSE</span></span>|<span data-ttu-id="eede9-114">`celt`Sono stati ignorati meno di elementi, a indicare che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="eede9-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eede9-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eede9-115">Remarks</span></span>  
 <span data-ttu-id="eede9-116">La nuova posizione del cursore di questo enumeratore è (posizione corrente) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="eede9-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eede9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eede9-117">Requirements</span></span>  
 <span data-ttu-id="eede9-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eede9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eede9-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eede9-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eede9-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eede9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eede9-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eede9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eede9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eede9-122">See also</span></span>

- [<span data-ttu-id="eede9-123">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="eede9-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="eede9-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="eede9-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
