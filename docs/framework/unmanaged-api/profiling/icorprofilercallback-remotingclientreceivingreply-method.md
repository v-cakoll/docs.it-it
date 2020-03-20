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
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175135"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="3616d-102">Metodo ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="3616d-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="3616d-103">Notifica al profiler che la parte lato server di una chiamata remota è stata completata e che il client sta ora ricevendo e sta per elaborare la risposta.</span><span class="sxs-lookup"><span data-stu-id="3616d-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3616d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3616d-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="3616d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3616d-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="3616d-106">[in] Valore che corrisponderà al valore fornito in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3616d-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="3616d-107">I cookie GUID remoti sono attivi.</span><span class="sxs-lookup"><span data-stu-id="3616d-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="3616d-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="3616d-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="3616d-109">I cookie GUID sono attivi nel processo lato server.</span><span class="sxs-lookup"><span data-stu-id="3616d-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="3616d-110">Ciò consente un facile accoppiamento delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="3616d-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="3616d-111">[in] Valore che `true` è se la chiamata è asincrona; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="3616d-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3616d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3616d-112">Requirements</span></span>  
 <span data-ttu-id="3616d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3616d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3616d-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3616d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3616d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3616d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3616d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3616d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3616d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3616d-117">See also</span></span>

- [<span data-ttu-id="3616d-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3616d-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
