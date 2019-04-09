---
title: Metodo ICorProfilerCallback::RemotingServerReceivingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30015cc6cae935c43cdbfec1a6eeae5c703ef9f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103207"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="ba388-102">Metodo ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="ba388-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="ba388-103">Notifica al profiler che il processo ha ricevuto una richiesta di attivazione o chiamata al metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="ba388-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba388-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba388-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba388-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba388-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ba388-106">[in] Un valore che corrisponde al valore fornito [RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="ba388-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="ba388-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="ba388-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="ba388-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ba388-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="ba388-109">I cookie GUID sono attivi nel processo del lato client.</span><span class="sxs-lookup"><span data-stu-id="ba388-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="ba388-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamate logici.</span><span class="sxs-lookup"><span data-stu-id="ba388-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ba388-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ba388-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba388-112">Note</span><span class="sxs-lookup"><span data-stu-id="ba388-112">Remarks</span></span>  
 <span data-ttu-id="ba388-113">Se il messaggio di richiesta è asincrona, la richiesta può essere gestita da qualsiasi thread arbitrario.</span><span class="sxs-lookup"><span data-stu-id="ba388-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba388-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba388-114">Requirements</span></span>  
 <span data-ttu-id="ba388-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba388-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba388-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba388-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba388-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba388-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ba388-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ba388-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba388-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba388-119">See also</span></span>

- [<span data-ttu-id="ba388-120">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ba388-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
