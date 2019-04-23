---
title: Metodo ICorProfilerCallback::RemotingServerSendingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024b1f3f7e08dc21582789de7f3899e8e44d5e39
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162685"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="52001-102">Metodo ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="52001-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="52001-103">Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remote e sta per trasmettere la risposta tramite un canale.</span><span class="sxs-lookup"><span data-stu-id="52001-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52001-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52001-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52001-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52001-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="52001-106">[in] Un puntatore a un GUID che corrisponde al valore fornito [RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="52001-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="52001-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="52001-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="52001-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="52001-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="52001-109">I cookie GUID sono attivi nel processo del lato client.</span><span class="sxs-lookup"><span data-stu-id="52001-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="52001-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamate logici.</span><span class="sxs-lookup"><span data-stu-id="52001-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="52001-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="52001-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52001-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52001-112">Requirements</span></span>  
 <span data-ttu-id="52001-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52001-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52001-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52001-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52001-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52001-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52001-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52001-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52001-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52001-117">See also</span></span>

- [<span data-ttu-id="52001-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="52001-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
