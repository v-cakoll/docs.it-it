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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a28b9d6e41d0572d423576f5b4024a60a70216c
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456870"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="34410-102">Funzione CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="34410-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="34410-103">Forza common language runtime (CLR) per rilasciare tutti i puntatori di interfaccia che vengono mantenuti all'interno di runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="34410-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="34410-104">Questo ha l'effetto di rilascio di tutte le cache RCW.</span><span class="sxs-lookup"><span data-stu-id="34410-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="34410-105">Questa funzione globale è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34410-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="34410-106">Usare invece il punto di ingresso per un runtime specifico.</span><span class="sxs-lookup"><span data-stu-id="34410-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34410-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34410-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="34410-108">Note</span><span class="sxs-lookup"><span data-stu-id="34410-108">Remarks</span></span>  
 <span data-ttu-id="34410-109">Il `CoEEShutDownCOM` funzione prima di tutto rilascia tutti i RCW in tutti i contesti e in tutte le cache e quindi rimuove qualsiasi notifica di chiusura esistente nel programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="34410-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="34410-110">Non lo scaricamento di DLL si verifica.</span><span class="sxs-lookup"><span data-stu-id="34410-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="34410-111">Questa funzione influisce su tutti i runtime caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="34410-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="34410-112">A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione runtime specifico che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="34410-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="34410-113">Per ottenere il punto di ingresso, chiamare il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e specificare "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="34410-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34410-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34410-114">Requirements</span></span>  
 <span data-ttu-id="34410-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34410-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34410-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="34410-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34410-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="34410-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34410-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34410-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34410-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34410-119">See also</span></span>

- [<span data-ttu-id="34410-120">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="34410-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
