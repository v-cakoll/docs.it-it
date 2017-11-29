---
title: Funzione CoEEShutDownCOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="83d09-102">Funzione CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="83d09-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="83d09-103">Impone a common language runtime (CLR) per rilasciare tutti i puntatori di interfaccia, contiene all'interno di runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="83d09-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="83d09-104">Questo ha l'effetto di rilascio di tutte le cache RCW.</span><span class="sxs-lookup"><span data-stu-id="83d09-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="83d09-105">Questa funzione globale è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83d09-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="83d09-106">Utilizzare invece il punto di ingresso per una specifica del runtime.</span><span class="sxs-lookup"><span data-stu-id="83d09-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d09-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83d09-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="83d09-108">Note</span><span class="sxs-lookup"><span data-stu-id="83d09-108">Remarks</span></span>  
 <span data-ttu-id="83d09-109">Il `CoEEShutDownCOM` funzione innanzitutto rilascia tutti i RCW in tutti i contesti e in tutte le cache e quindi rimuove qualsiasi notifica di chiusura esistente nel programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="83d09-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="83d09-110">Non lo scaricamento di DLL si verifica.</span><span class="sxs-lookup"><span data-stu-id="83d09-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="83d09-111">Questa funzione influisce su tutti i runtime caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="83d09-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="83d09-112">A partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], chiamare il punto di ingresso per questa funzione sull'ambiente di esecuzione specifico che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="83d09-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="83d09-113">Per ottenere il punto di ingresso, chiamare il [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e specificare "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="83d09-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d09-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83d09-114">Requirements</span></span>  
 <span data-ttu-id="83d09-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83d09-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d09-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83d09-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83d09-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83d09-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83d09-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d09-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83d09-119">See Also</span></span>  
 [<span data-ttu-id="83d09-120">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="83d09-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
