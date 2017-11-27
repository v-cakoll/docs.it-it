---
title: Metodo ICorProfilerCallback::RemotingClientReceivingReply
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f1dd027dc113abfceeb88abbc82c69ed395584e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="ce708-102">Metodo ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="ce708-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="ce708-103">Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client è ora di ricezione e sta per elaborare la risposta.</span><span class="sxs-lookup"><span data-stu-id="ce708-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce708-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce708-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce708-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce708-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ce708-106">[in] Un valore che corrisponde al valore fornito [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="ce708-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="ce708-107">I cookie dei GUID remoti sono attive.</span><span class="sxs-lookup"><span data-stu-id="ce708-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="ce708-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ce708-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="ce708-109">I cookie GUID sono attivi sul processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="ce708-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="ce708-110">Ciò consente l'associazione semplice delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="ce708-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ce708-111">[in] Un valore che è `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ce708-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce708-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce708-112">Requirements</span></span>  
 <span data-ttu-id="ce708-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce708-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce708-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce708-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce708-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce708-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce708-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce708-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce708-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce708-117">See Also</span></span>  
 [<span data-ttu-id="ce708-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ce708-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
