---
title: Metodo ICorProfilerCallback::RemotingServerSendingReply
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerSendingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b99b2de235634b715a6f5ba9fee9ee49ab34063a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="ec868-102">Metodo ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="ec868-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="ec868-103">Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata di metodo remoto e sta per trasmettere la risposta tramite un canale.</span><span class="sxs-lookup"><span data-stu-id="ec868-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec868-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec868-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec868-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec868-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ec868-106">[in] Un puntatore a un GUID che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="ec868-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="ec868-107">I cookie dei GUID remoti sono attive.</span><span class="sxs-lookup"><span data-stu-id="ec868-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="ec868-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec868-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="ec868-109">I cookie GUID sono attivi sul processo del lato client.</span><span class="sxs-lookup"><span data-stu-id="ec868-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="ec868-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamata logico.</span><span class="sxs-lookup"><span data-stu-id="ec868-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ec868-111">[in] Un valore che è `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ec868-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec868-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec868-112">Requirements</span></span>  
 <span data-ttu-id="ec868-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec868-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec868-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec868-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec868-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec868-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec868-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec868-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec868-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec868-117">See Also</span></span>  
 [<span data-ttu-id="ec868-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ec868-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
