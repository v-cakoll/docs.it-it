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
ms.openlocfilehash: bf59d4e418223fd177bc5e19b173674b78e1f2ba
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499922"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="b9351-102">Metodo ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="b9351-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="b9351-103">Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remoto e sta per trasmettere la risposta tramite un canale.</span><span class="sxs-lookup"><span data-stu-id="b9351-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9351-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9351-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9351-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9351-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="b9351-106">in Puntatore a un GUID che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="b9351-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="b9351-107">I cookie GUID di comunicazione remota sono attivi.</span><span class="sxs-lookup"><span data-stu-id="b9351-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="b9351-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b9351-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="b9351-109">I cookie GUID sono attivi sul processo sul lato client.</span><span class="sxs-lookup"><span data-stu-id="b9351-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="b9351-110">Questo consente di associare facilmente le chiamate remote e la creazione di uno stack di chiamate logico.</span><span class="sxs-lookup"><span data-stu-id="b9351-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b9351-111">in Valore che è `true` se la chiamata è asincrona; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="b9351-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9351-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9351-112">Requirements</span></span>  
 <span data-ttu-id="b9351-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9351-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9351-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9351-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9351-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9351-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9351-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9351-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9351-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9351-117">See also</span></span>

- [<span data-ttu-id="b9351-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b9351-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
