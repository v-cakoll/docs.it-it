---
title: Enumerazione CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
ms.openlocfilehash: b9185600d9d8b2a33830d86642727ac54b87a9cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099649"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="758e3-102">Enumerazione CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="758e3-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="758e3-103">Fornisce i valori utilizzati dal metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="758e3-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="758e3-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="758e3-105">Members</span><span class="sxs-lookup"><span data-stu-id="758e3-105">Members</span></span>  
  
|<span data-ttu-id="758e3-106">Member</span><span class="sxs-lookup"><span data-stu-id="758e3-106">Member</span></span>|<span data-ttu-id="758e3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="758e3-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="758e3-108">Questo runtime include un evento debugger gestito non di recupero da inviare.</span><span class="sxs-lookup"><span data-stu-id="758e3-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="758e3-109">Vedere la sezione Osservazioni per la distinzione tra eventi di recupero e non di recupero.</span><span class="sxs-lookup"><span data-stu-id="758e3-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="758e3-110">L'evento gestito in sospeso è una richiesta <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="758e3-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="758e3-111">Note</span><span class="sxs-lookup"><span data-stu-id="758e3-111">Remarks</span></span>  
 <span data-ttu-id="758e3-112">Gli eventi di aggiornamento includono le notifiche relative a processo, dominio applicazione, assembly, modulo e creazione thread che consentono al debugger di raggiungere lo stato corrente dopo che è stato collegato a un processo.</span><span class="sxs-lookup"><span data-stu-id="758e3-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="758e3-113">Gli eventi non di recupero, indicati dal flag `CLR_DEBUGGING_MANAGED_EVENT_PENDING`, includono tutti gli altri eventi del debugger, ad esempio le eccezioni e le notifiche dell'assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="758e3-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="758e3-114">Il flag `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` consente al runtime di distinguere tra un'eccezione di terminazione e una richiesta di associazione di un debugger gestito che può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="758e3-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="758e3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="758e3-115">Requirements</span></span>  
 <span data-ttu-id="758e3-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="758e3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="758e3-117">**Intestazione:** Metahost. idl, Metahost. h</span><span class="sxs-lookup"><span data-stu-id="758e3-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="758e3-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="758e3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="758e3-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="758e3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758e3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="758e3-120">See also</span></span>

- [<span data-ttu-id="758e3-121">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="758e3-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="758e3-122">Debug</span><span class="sxs-lookup"><span data-stu-id="758e3-122">Debugging</span></span>](index.md)
