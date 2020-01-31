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
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865974"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="e8a0a-102">Metodo ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="e8a0a-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="e8a0a-103">Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remoto e sta per trasmettere la risposta tramite un canale.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8a0a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8a0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8a0a-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="e8a0a-106">in Puntatore a un GUID che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="e8a0a-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="e8a0a-107">I cookie GUID di comunicazione remota sono attivi.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="e8a0a-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="e8a0a-109">I cookie GUID sono attivi sul processo sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="e8a0a-110">Questo consente di associare facilmente le chiamate remote e la creazione di uno stack di chiamate logico.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="e8a0a-111">in Valore `true` se la chiamata è asincrona. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e8a0a-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a0a-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e8a0a-112">Requirements</span></span>  
 <span data-ttu-id="e8a0a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8a0a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a0a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8a0a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8a0a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8a0a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8a0a-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a0a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a0a-117">See also</span></span>

- [<span data-ttu-id="e8a0a-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e8a0a-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
