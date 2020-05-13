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
ms.openlocfilehash: 4d954057c519263da49f8aaeeeef6ab9402b6956
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378366"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="8a212-102">Metodo ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="8a212-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="8a212-103">Indica se il thread ha già avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8a212-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a212-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a212-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a212-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a212-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="8a212-106">out Puntatore all'indirizzo di un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="8a212-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a212-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a212-107">Return Value</span></span>  
 <span data-ttu-id="8a212-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8a212-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a212-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a212-109">HRESULT</span></span>|<span data-ttu-id="8a212-110">Description</span><span class="sxs-lookup"><span data-stu-id="8a212-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a212-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a212-111">S_OK</span></span>|<span data-ttu-id="8a212-112">Si è verificata un'eccezione non gestita dal thread dopo la relativa creazione.</span><span class="sxs-lookup"><span data-stu-id="8a212-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="8a212-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8a212-113">S_FALSE</span></span>|<span data-ttu-id="8a212-114">Il thread non ha mai avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8a212-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a212-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8a212-115">Remarks</span></span>  
 <span data-ttu-id="8a212-116">Questo metodo indica se il thread ha mai avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8a212-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="8a212-117">Al momento dell'attivazione del callback di eccezione non gestita o dell'avvio della connessione JIT nativa, questo metodo garantisce che venga restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="8a212-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="8a212-118">Non esiste alcuna garanzia che il metodo [ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md) restituisca l'eccezione non gestita. Tuttavia, se il processo non è ancora stato proseguito dopo aver ricevuto il callback di eccezione non gestita o dopo la connessione JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="8a212-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="8a212-119">Inoltre, è possibile, anche se improbabile, avere più di un thread con un'eccezione non gestita al momento dell'attivazione della connessione JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="8a212-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="8a212-120">In tal caso non è possibile determinare l'eccezione che ha attivato la connessione JIT.</span><span class="sxs-lookup"><span data-stu-id="8a212-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a212-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a212-121">Requirements</span></span>  
 <span data-ttu-id="8a212-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a212-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a212-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a212-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a212-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a212-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a212-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a212-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a212-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a212-126">See also</span></span>

- [<span data-ttu-id="8a212-127">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="8a212-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="8a212-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8a212-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a212-129">Debug</span><span class="sxs-lookup"><span data-stu-id="8a212-129">Debugging</span></span>](index.md)
