---
title: Metodo ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61a36ff23bf9deac25983f06387b2bbbfd49546b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133185"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="d80d1-102">Metodo ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="d80d1-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="d80d1-103">Notifica al profiler che il client stia inviando una richiesta al server.</span><span class="sxs-lookup"><span data-stu-id="d80d1-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d80d1-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d80d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d80d1-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="d80d1-106">[in] Un valore che corrisponde al valore fornito [RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="d80d1-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="d80d1-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="d80d1-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="d80d1-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d80d1-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="d80d1-109">I cookie GUID sono attivi nel processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="d80d1-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="d80d1-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamate logici.</span><span class="sxs-lookup"><span data-stu-id="d80d1-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="d80d1-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d80d1-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d80d1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d80d1-112">Requirements</span></span>  
 <span data-ttu-id="d80d1-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d80d1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d80d1-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d80d1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d80d1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d80d1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d80d1-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d80d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80d1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d80d1-117">See also</span></span>

- [<span data-ttu-id="d80d1-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d80d1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
