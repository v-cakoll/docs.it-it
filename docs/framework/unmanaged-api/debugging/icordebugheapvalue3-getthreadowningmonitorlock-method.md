---
title: Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: 9cc68e39dfef096b8ab6a8ba743f7a516cc349be
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210410"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="9b41b-102">Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="9b41b-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="9b41b-103">Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b41b-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b41b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b41b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b41b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b41b-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="9b41b-106">out Thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b41b-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="9b41b-107">out Il numero di volte in cui il thread deve rilasciare il blocco prima che torni a essere senza proprietario.</span><span class="sxs-lookup"><span data-stu-id="9b41b-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b41b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b41b-108">Return Value</span></span>  
 <span data-ttu-id="9b41b-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9b41b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9b41b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b41b-110">HRESULT</span></span>|<span data-ttu-id="9b41b-111">Description</span><span class="sxs-lookup"><span data-stu-id="9b41b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b41b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b41b-112">S_OK</span></span>|<span data-ttu-id="9b41b-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9b41b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9b41b-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9b41b-114">S_FALSE</span></span>|<span data-ttu-id="9b41b-115">Nessun thread gestito è proprietario del blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b41b-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9b41b-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="9b41b-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b41b-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b41b-117">Remarks</span></span>  
 <span data-ttu-id="9b41b-118">Se un thread gestito è proprietario del blocco di monitoraggio su questo oggetto:</span><span class="sxs-lookup"><span data-stu-id="9b41b-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="9b41b-119">Il metodo restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="9b41b-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="9b41b-120">L'oggetto thread è valido fino alla chiusura del thread.</span><span class="sxs-lookup"><span data-stu-id="9b41b-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="9b41b-121">Se nessun thread gestito è proprietario del blocco di monitoraggio su questo oggetto `ppThread` e non `pAcquisitionCount` è stato modificato e il metodo restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="9b41b-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="9b41b-122">Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="9b41b-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="9b41b-123">Se si verifica un errore in modo che non sia possibile determinare quale thread è proprietario del blocco di monitoraggio su questo oggetto, il metodo restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="9b41b-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b41b-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b41b-124">Requirements</span></span>  
 <span data-ttu-id="9b41b-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b41b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b41b-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b41b-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b41b-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b41b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b41b-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b41b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b41b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b41b-129">See also</span></span>

- [<span data-ttu-id="9b41b-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9b41b-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9b41b-131">Debug</span><span class="sxs-lookup"><span data-stu-id="9b41b-131">Debugging</span></span>](index.md)
