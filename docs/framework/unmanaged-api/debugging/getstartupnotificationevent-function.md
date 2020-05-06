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
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860705"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="9018a-102">Funzione GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="9018a-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="9018a-103">Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="9018a-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9018a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9018a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9018a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9018a-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="9018a-106">[in] Identificatore del processo di destinazione da cui ricevere le notifiche di avvio CLR.</span><span class="sxs-lookup"><span data-stu-id="9018a-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="9018a-107">[out] Puntatore a un handle che verrà segnalato da CLR all'avvio.</span><span class="sxs-lookup"><span data-stu-id="9018a-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9018a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9018a-108">Return Value</span></span>  
 <span data-ttu-id="9018a-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9018a-109">S_OK</span></span>  
 <span data-ttu-id="9018a-110">L'handle all'evento di notifica di avvio è stato ottenuto correttamente.</span><span class="sxs-lookup"><span data-stu-id="9018a-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="9018a-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9018a-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="9018a-112">`phStartupEvent` è null o `debuggeePID` non fa riferimento a un processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9018a-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="9018a-113">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="9018a-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9018a-114">Non è possibile ottenere l'handle all'evento di notifica di avvio.</span><span class="sxs-lookup"><span data-stu-id="9018a-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9018a-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9018a-115">Remarks</span></span>  
 <span data-ttu-id="9018a-116">Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9018a-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="9018a-117">L'evento viene segnalato prima che qualsiasi codice gestito venga eseguito dal CLR che ha segnalato l'evento.</span><span class="sxs-lookup"><span data-stu-id="9018a-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9018a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9018a-118">Requirements</span></span>  
 <span data-ttu-id="9018a-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9018a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9018a-120">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="9018a-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9018a-121">**Libreria:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="9018a-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9018a-122">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9018a-122">**.NET Framework Versions:** 3.5 SP1</span></span>
