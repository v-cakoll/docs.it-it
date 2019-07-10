---
title: Funzione GetStartupNotificationEvent
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f67f3ef57b4996eb4a956c596b76fb94b1bdfd7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738893"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="d9ae6-102">Funzione GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="d9ae6-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="d9ae6-103">Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ae6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9ae6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ae6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9ae6-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="d9ae6-106">[in] Identificatore del processo di destinazione da cui ricevere le notifiche di avvio CLR.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="d9ae6-107">[out] Puntatore a un handle che verrà segnalato da CLR all'avvio.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9ae6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d9ae6-108">Return Value</span></span>  
 <span data-ttu-id="d9ae6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9ae6-109">S_OK</span></span>  
 <span data-ttu-id="d9ae6-110">L'handle all'evento di notifica di avvio è stato ottenuto correttamente.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="d9ae6-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d9ae6-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="d9ae6-112">`phStartupEvent` è null o `debuggeePID` non fa riferimento a un processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="d9ae6-113">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="d9ae6-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d9ae6-114">Non è possibile ottenere l'handle all'evento di notifica di avvio.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9ae6-115">Note</span><span class="sxs-lookup"><span data-stu-id="d9ae6-115">Remarks</span></span>  
 <span data-ttu-id="d9ae6-116">Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="d9ae6-117">L'evento viene segnalato prima che qualsiasi codice gestito venga eseguito dal CLR che ha segnalato l'evento.</span><span class="sxs-lookup"><span data-stu-id="d9ae6-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ae6-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9ae6-118">Requirements</span></span>  
 <span data-ttu-id="d9ae6-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9ae6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ae6-120">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="d9ae6-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="d9ae6-121">**Libreria:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="d9ae6-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="d9ae6-122">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d9ae6-122">**.NET Framework Versions:** 3.5 SP1</span></span>
