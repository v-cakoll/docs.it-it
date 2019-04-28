---
title: Metodo ICorProfilerCallback::RemotingClientReceivingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5865935af96260982d47b778d208f4235f6245e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775025"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="a6c8d-102">Metodo ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="a6c8d-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="a6c8d-103">Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client sta ricevendo ora e sta per elaborare la risposta.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6c8d-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a6c8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6c8d-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="a6c8d-106">[in] Un valore che corrisponde al valore fornito [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="a6c8d-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="a6c8d-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="a6c8d-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="a6c8d-109">I cookie GUID sono attivi nel processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="a6c8d-110">Ciò consente l'associazione semplice delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="a6c8d-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a6c8d-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6c8d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6c8d-112">Requirements</span></span>  
 <span data-ttu-id="a6c8d-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6c8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6c8d-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6c8d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6c8d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6c8d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6c8d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6c8d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c8d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6c8d-117">See also</span></span>

- [<span data-ttu-id="a6c8d-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a6c8d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
