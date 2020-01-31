---
title: Metodo ICorDebugThread4::HadUnhandledException
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: f558a4c94afeb69f58605958ddcb91e4be772c39
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791343"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="aa119-102">Metodo ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="aa119-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="aa119-103">Indica se il thread ha già avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="aa119-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa119-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa119-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa119-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa119-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="aa119-106">out Puntatore all'indirizzo di un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="aa119-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa119-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aa119-107">Return Value</span></span>  
 <span data-ttu-id="aa119-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="aa119-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="aa119-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa119-109">HRESULT</span></span>|<span data-ttu-id="aa119-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa119-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa119-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa119-111">S_OK</span></span>|<span data-ttu-id="aa119-112">Si è verificata un'eccezione non gestita dal thread dopo la relativa creazione.</span><span class="sxs-lookup"><span data-stu-id="aa119-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="aa119-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="aa119-113">S_FALSE</span></span>|<span data-ttu-id="aa119-114">Il thread non ha mai avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="aa119-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa119-115">Note</span><span class="sxs-lookup"><span data-stu-id="aa119-115">Remarks</span></span>  
 <span data-ttu-id="aa119-116">Questo metodo indica se il thread ha mai avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="aa119-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="aa119-117">Al momento dell'attivazione del callback di eccezione non gestita o dell'avvio della connessione JIT nativa, questo metodo garantisce che venga restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="aa119-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="aa119-118">Non esiste alcuna garanzia che il metodo [ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md) restituisca l'eccezione non gestita. Tuttavia, se il processo non è ancora stato proseguito dopo aver ricevuto il callback di eccezione non gestita o dopo la connessione JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="aa119-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="aa119-119">Inoltre, è possibile, anche se improbabile, avere più di un thread con un'eccezione non gestita al momento dell'attivazione della connessione JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="aa119-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="aa119-120">In tal caso non è possibile determinare l'eccezione che ha attivato la connessione JIT.</span><span class="sxs-lookup"><span data-stu-id="aa119-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa119-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="aa119-121">Requirements</span></span>  
 <span data-ttu-id="aa119-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa119-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa119-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa119-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa119-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa119-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa119-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa119-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa119-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa119-126">See also</span></span>

- [<span data-ttu-id="aa119-127">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="aa119-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="aa119-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="aa119-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="aa119-129">Debug</span><span class="sxs-lookup"><span data-stu-id="aa119-129">Debugging</span></span>](index.md)
