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
ms.openlocfilehash: 157e6bc6cb9603fa9558ad6d39f0b086849fc7b0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499896"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="7f3d6-102">Metodo ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="7f3d6-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="7f3d6-103">Notifica al profiler che il processo ha ricevuto una chiamata al metodo remoto o una richiesta di attivazione.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f3d6-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f3d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f3d6-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="7f3d6-106">in Valore che corrisponderà al valore fornito in [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="7f3d6-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="7f3d6-107">I cookie GUID di comunicazione remota sono attivi.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="7f3d6-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="7f3d6-109">I cookie GUID sono attivi sul processo sul lato client.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="7f3d6-110">Questo consente di associare facilmente le chiamate remote e la creazione di uno stack di chiamate logico.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="7f3d6-111">in Valore che è `true` se la chiamata è asincrona; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="7f3d6-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f3d6-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7f3d6-112">Remarks</span></span>  
 <span data-ttu-id="7f3d6-113">Se la richiesta di messaggio è asincrona, la richiesta può essere gestita da qualsiasi thread arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7f3d6-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f3d6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f3d6-114">Requirements</span></span>  
 <span data-ttu-id="7f3d6-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f3d6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f3d6-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f3d6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f3d6-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f3d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f3d6-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f3d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f3d6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f3d6-119">See also</span></span>

- [<span data-ttu-id="7f3d6-120">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7f3d6-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
