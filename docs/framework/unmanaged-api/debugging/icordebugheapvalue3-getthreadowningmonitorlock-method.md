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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1678f1de7c23387f028348dadbc7b61e2cdc035c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201429"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="51a7e-102">Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="51a7e-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="51a7e-103">Restituisce il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="51a7e-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51a7e-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51a7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51a7e-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="51a7e-106">[out] Il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="51a7e-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="51a7e-107">[out] Il numero di volte in cui che il thread dovrà rilasciare il blocco prima di restituire a essere senza proprietario.</span><span class="sxs-lookup"><span data-stu-id="51a7e-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51a7e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51a7e-108">Return Value</span></span>  
 <span data-ttu-id="51a7e-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="51a7e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="51a7e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51a7e-110">HRESULT</span></span>|<span data-ttu-id="51a7e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a7e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51a7e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="51a7e-112">S_OK</span></span>|<span data-ttu-id="51a7e-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="51a7e-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="51a7e-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="51a7e-114">S_FALSE</span></span>|<span data-ttu-id="51a7e-115">Nessun thread gestito possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="51a7e-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="51a7e-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="51a7e-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51a7e-117">Note</span><span class="sxs-lookup"><span data-stu-id="51a7e-117">Remarks</span></span>  
 <span data-ttu-id="51a7e-118">Se un thread gestito è il proprietario del blocco di monitoraggio per questo oggetto:</span><span class="sxs-lookup"><span data-stu-id="51a7e-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="51a7e-119">Il metodo restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="51a7e-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="51a7e-120">L'oggetto thread è valido fino a quando la chiusura del thread.</span><span class="sxs-lookup"><span data-stu-id="51a7e-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="51a7e-121">Se nessun thread gestito possiede il blocco di monitoraggio tohoto objektu `ppThread` e `pAcquisitionCount` rimangono invariati, e il metodo restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="51a7e-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="51a7e-122">Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="51a7e-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="51a7e-123">Se si verifica un errore in modo che non può essere determinato che, se presente, thread proprietario del blocco di monitoraggio per l'oggetto, il metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="51a7e-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51a7e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51a7e-124">Requirements</span></span>  
 <span data-ttu-id="51a7e-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51a7e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51a7e-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51a7e-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51a7e-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51a7e-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="51a7e-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51a7e-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51a7e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51a7e-129">See also</span></span>

- [<span data-ttu-id="51a7e-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="51a7e-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="51a7e-131">Debug</span><span class="sxs-lookup"><span data-stu-id="51a7e-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
