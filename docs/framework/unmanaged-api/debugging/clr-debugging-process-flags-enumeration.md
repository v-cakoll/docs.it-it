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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274107"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="ab6b9-102">Enumerazione CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="ab6b9-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="ab6b9-103">Fornisce i valori utilizzati dal metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ab6b9-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab6b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab6b9-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ab6b9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ab6b9-105">Members</span></span>  
  
|<span data-ttu-id="ab6b9-106">Member</span><span class="sxs-lookup"><span data-stu-id="ab6b9-106">Member</span></span>|<span data-ttu-id="ab6b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab6b9-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="ab6b9-108">Questo runtime include un evento debugger gestito non di recupero da inviare.</span><span class="sxs-lookup"><span data-stu-id="ab6b9-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="ab6b9-109">Vedere la sezione Osservazioni per la distinzione tra eventi di recupero e non di recupero.</span><span class="sxs-lookup"><span data-stu-id="ab6b9-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="ab6b9-110">L'evento gestito in sospeso è una <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> richiesta.</span><span class="sxs-lookup"><span data-stu-id="ab6b9-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab6b9-111">Note</span><span class="sxs-lookup"><span data-stu-id="ab6b9-111">Remarks</span></span>  
 <span data-ttu-id="ab6b9-112">Gli eventi di aggiornamento includono le notifiche relative a processo, dominio applicazione, assembly, modulo e creazione thread che consentono al debugger di raggiungere lo stato corrente dopo che è stato collegato a un processo.</span><span class="sxs-lookup"><span data-stu-id="ab6b9-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="ab6b9-113">Gli eventi non di recupero, indicati dal `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, includono tutti gli altri eventi del debugger, ad esempio le eccezioni e le notifiche dell'assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="ab6b9-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="ab6b9-114">Il `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag consente al runtime di distinguere tra un'eccezione di terminazione e una richiesta di associazione di un debugger gestito che può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="ab6b9-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab6b9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab6b9-115">Requirements</span></span>  
 <span data-ttu-id="ab6b9-116">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab6b9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab6b9-117">**Intestazione:** Metahost. idl, Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ab6b9-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="ab6b9-118">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab6b9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab6b9-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab6b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab6b9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab6b9-120">See also</span></span>

- [<span data-ttu-id="ab6b9-121">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ab6b9-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="ab6b9-122">Debug</span><span class="sxs-lookup"><span data-stu-id="ab6b9-122">Debugging</span></span>](index.md)
