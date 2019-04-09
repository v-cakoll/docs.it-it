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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133185"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="a4472-102">Metodo ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="a4472-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="a4472-103">Notifica al profiler che il client stia inviando una richiesta al server.</span><span class="sxs-lookup"><span data-stu-id="a4472-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4472-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4472-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4472-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4472-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="a4472-106">[in] Un valore che corrisponde al valore fornito [RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="a4472-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="a4472-107">I cookie GUID di .NET Remoting sono attivi.</span><span class="sxs-lookup"><span data-stu-id="a4472-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="a4472-108">Il canale ha esito positivo la trasmissione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a4472-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="a4472-109">I cookie GUID sono attivi nel processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="a4472-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="a4472-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamate logici.</span><span class="sxs-lookup"><span data-stu-id="a4472-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="a4472-111">[in] Valore che rappresenta `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a4472-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4472-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4472-112">Requirements</span></span>  
 <span data-ttu-id="a4472-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4472-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4472-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4472-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4472-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4472-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4472-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a4472-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4472-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4472-117">See also</span></span>

- [<span data-ttu-id="a4472-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a4472-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
