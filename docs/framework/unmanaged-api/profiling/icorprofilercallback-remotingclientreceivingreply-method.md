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
ms.openlocfilehash: 2134a7f12ac482b3fe79ac722684ac8601a7280b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662928"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="b7ec3-102">Metodo ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="b7ec3-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="b7ec3-103">Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client sta ricevendo ora e sta per elaborare la risposta.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ec3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7ec3-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b7ec3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7ec3-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="b7ec3-106">[in] Un valore che corrisponde al valore fornito [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="b7ec3-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="b7ec3-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="b7ec3-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="b7ec3-109">I cookie GUID sono attivi nel processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="b7ec3-110">Ciò consente l'associazione semplice delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b7ec3-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ec3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7ec3-112">Requirements</span></span>  
 <span data-ttu-id="b7ec3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ec3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ec3-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7ec3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7ec3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7ec3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7ec3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ec3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ec3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7ec3-117">See also</span></span>

- [<span data-ttu-id="b7ec3-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b7ec3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
