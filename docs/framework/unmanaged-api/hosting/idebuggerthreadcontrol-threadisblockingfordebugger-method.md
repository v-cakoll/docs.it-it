---
title: Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: f7cdc3fe9d52db56d0280bc602d3a9f2f54e8246
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805258"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="4ff44-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="4ff44-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="4ff44-103">Notifica all'host che il thread che sta inviando questo callback sta per bloccarsi nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="4ff44-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ff44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ff44-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ff44-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4ff44-105">Remarks</span></span>  
 <span data-ttu-id="4ff44-106">Il `ThreadIsBlockingForDebugger` metodo verrà sempre chiamato su un thread di Runtime.</span><span class="sxs-lookup"><span data-stu-id="4ff44-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="4ff44-107">Il `ThreadIsBlockingForDebugger` metodo offre all'host la possibilità di eseguire un'altra azione durante il blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="4ff44-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff44-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ff44-108">Requirements</span></span>  
 <span data-ttu-id="4ff44-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff44-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff44-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4ff44-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ff44-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ff44-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ff44-112">**Versioni di .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff44-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff44-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ff44-113">See also</span></span>

- [<span data-ttu-id="4ff44-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="4ff44-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
