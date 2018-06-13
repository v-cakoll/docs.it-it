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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8215ddfd0f59f835d0b0dcd278b8cae9c12027d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422110"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="dde34-102">Metodo ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="dde34-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="dde34-103">Indica se il thread è già verificata un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="dde34-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dde34-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dde34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dde34-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="dde34-106">[out] Un puntatore all'indirizzo di un'enumerazione ordinata di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="dde34-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dde34-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dde34-107">Return Value</span></span>  
 <span data-ttu-id="dde34-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="dde34-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dde34-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dde34-109">HRESULT</span></span>|<span data-ttu-id="dde34-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dde34-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dde34-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dde34-111">S_OK</span></span>|<span data-ttu-id="dde34-112">Il thread è verificata un'eccezione non gestita dal momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="dde34-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="dde34-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="dde34-113">S_FALSE</span></span>|<span data-ttu-id="dde34-114">Il thread non è stato mai un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="dde34-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde34-115">Note</span><span class="sxs-lookup"><span data-stu-id="dde34-115">Remarks</span></span>  
 <span data-ttu-id="dde34-116">Questo metodo indica se il thread è già verificata un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="dde34-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="dde34-117">Quando viene attivato il callback di eccezione non gestita o native ad associazione JIT viene avviato, viene garantito che questo metodo per restituire S_OK.</span><span class="sxs-lookup"><span data-stu-id="dde34-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="dde34-118">Non c'è garanzia che il [ICorDebugThread. GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) metodo restituirà l'eccezione non gestita; tuttavia, verranno eseguite se il processo non ancora ripreso dopo aver ottenuto il callback di eccezione non gestita o dopo il associazione JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="dde34-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="dde34-119">Inoltre, è possibile (anche se improbabile) abbia più di un thread con un'eccezione non gestita in fase di associazione JIT nativa viene attivato.</span><span class="sxs-lookup"><span data-stu-id="dde34-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="dde34-120">In questo caso non è possibile determinare quale eccezione ha attivato l'associazione JIT.</span><span class="sxs-lookup"><span data-stu-id="dde34-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde34-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dde34-121">Requirements</span></span>  
 <span data-ttu-id="dde34-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde34-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde34-123">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="dde34-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dde34-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dde34-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde34-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde34-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde34-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dde34-126">See Also</span></span>  
 [<span data-ttu-id="dde34-127">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="dde34-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="dde34-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dde34-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dde34-129">Debug</span><span class="sxs-lookup"><span data-stu-id="dde34-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
