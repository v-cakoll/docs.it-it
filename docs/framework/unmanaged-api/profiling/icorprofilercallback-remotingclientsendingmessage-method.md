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
ms.openlocfilehash: 820a37c8ca16f4962bf1d72b1f0f404cffd92a1a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499961"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="30d08-102">Metodo ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="30d08-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="30d08-103">Notifica al profiler che il client sta inviando una richiesta al server.</span><span class="sxs-lookup"><span data-stu-id="30d08-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d08-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30d08-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30d08-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30d08-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="30d08-106">in Valore che corrisponde al valore fornito in [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="30d08-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="30d08-107">I cookie GUID di comunicazione remota sono attivi.</span><span class="sxs-lookup"><span data-stu-id="30d08-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="30d08-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="30d08-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="30d08-109">I cookie GUID sono attivi sul processo sul lato server.</span><span class="sxs-lookup"><span data-stu-id="30d08-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="30d08-110">Questo consente di associare facilmente le chiamate remote e la creazione di uno stack di chiamate logico.</span><span class="sxs-lookup"><span data-stu-id="30d08-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="30d08-111">in Valore che è `true` se la chiamata è asincrona; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="30d08-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30d08-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30d08-112">Requirements</span></span>  
 <span data-ttu-id="30d08-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d08-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d08-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30d08-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30d08-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30d08-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30d08-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d08-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d08-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30d08-117">See also</span></span>

- [<span data-ttu-id="30d08-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="30d08-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
