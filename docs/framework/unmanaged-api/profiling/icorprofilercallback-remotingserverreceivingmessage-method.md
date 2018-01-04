---
title: Metodo ICorProfilerCallback::RemotingServerReceivingMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerReceivingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4542f5362d83bc5c0419b9f1ff389c9a21aad29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="5bcb5-102">Metodo ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="5bcb5-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="5bcb5-103">Notifica al profiler che il processo ha ricevuto una richiesta di attivazione o la chiamata di metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcb5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bcb5-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bcb5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5bcb5-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="5bcb5-106">[in] Un valore che corrisponde al valore fornito [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="5bcb5-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="5bcb5-107">I cookie dei GUID remoti sono attive.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="5bcb5-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="5bcb5-109">I cookie GUID sono attivi sul processo del lato client.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="5bcb5-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamata logico.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="5bcb5-111">[in] Un valore che è `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bcb5-112">Note</span><span class="sxs-lookup"><span data-stu-id="5bcb5-112">Remarks</span></span>  
 <span data-ttu-id="5bcb5-113">Se la richiesta di messaggio è asincrona, la richiesta può essere gestita da un thread qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="5bcb5-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcb5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bcb5-114">Requirements</span></span>  
 <span data-ttu-id="5bcb5-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bcb5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bcb5-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bcb5-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bcb5-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bcb5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bcb5-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bcb5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcb5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bcb5-119">See Also</span></span>  
 [<span data-ttu-id="5bcb5-120">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5bcb5-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
