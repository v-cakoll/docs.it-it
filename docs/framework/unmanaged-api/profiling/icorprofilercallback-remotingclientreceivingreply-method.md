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
ms.openlocfilehash: 0a21924008bcbfa0894218f57aee559a564f8003
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499974"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="c6f2a-102">Metodo ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="c6f2a-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="c6f2a-103">Notifica al profiler che la parte lato server di una chiamata remota è stata completata e che il client sta ricevendo e sta per elaborare la risposta.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6f2a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6f2a-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="c6f2a-106">in Valore che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="c6f2a-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="c6f2a-107">I cookie GUID di comunicazione remota sono attivi.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="c6f2a-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="c6f2a-109">I cookie GUID sono attivi sul processo sul lato server.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="c6f2a-110">In questo modo è possibile associare agevolmente le chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="c6f2a-111">in Valore che è `true` se la chiamata è asincrona; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="c6f2a-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f2a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6f2a-112">Requirements</span></span>  
 <span data-ttu-id="c6f2a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f2a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6f2a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6f2a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6f2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f2a-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f2a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f2a-117">See also</span></span>

- [<span data-ttu-id="c6f2a-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c6f2a-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
