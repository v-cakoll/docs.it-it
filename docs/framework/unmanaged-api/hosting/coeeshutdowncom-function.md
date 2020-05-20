---
title: Funzione CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 3eb8bffee9d30a89c39a900e600ebf171456b9f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616788"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="20f9d-102">Funzione CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="20f9d-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="20f9d-103">Forza la Common Language Runtime (CLR) a rilasciare tutti i puntatori di interfaccia contenuti in Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="20f9d-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="20f9d-104">Questo ha l'effetto di rilasciare tutte le cache RCW.</span><span class="sxs-lookup"><span data-stu-id="20f9d-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="20f9d-105">Questa funzione globale è deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="20f9d-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="20f9d-106">Usare invece il punto di ingresso per un runtime specifico.</span><span class="sxs-lookup"><span data-stu-id="20f9d-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f9d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20f9d-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="20f9d-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20f9d-108">Remarks</span></span>  
 <span data-ttu-id="20f9d-109">La `CoEEShutDownCOM` funzione rilascia innanzitutto tutti i RCW in tutti i contesti e in tutte le cache, quindi rimuove eventuali notifiche di chiusura presenti nel programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="20f9d-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="20f9d-110">Non viene eseguito lo scaricamento della DLL.</span><span class="sxs-lookup"><span data-stu-id="20f9d-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="20f9d-111">Questa funzione ha effetto su tutti i runtime caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="20f9d-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="20f9d-112">A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione sul runtime specifico che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="20f9d-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="20f9d-113">Per ottenere il punto di ingresso, chiamare il metodo [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) e specificare "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="20f9d-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f9d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20f9d-114">Requirements</span></span>  
 <span data-ttu-id="20f9d-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20f9d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f9d-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="20f9d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20f9d-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="20f9d-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20f9d-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f9d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f9d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20f9d-119">See also</span></span>

- [<span data-ttu-id="20f9d-120">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="20f9d-120">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
