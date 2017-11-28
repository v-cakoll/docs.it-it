---
title: Interfaccia ICLRDebugging
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging
helpviewer_keywords: ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3e061b95faafeec3c3d233ab54f128a23c3264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="ae90f-102">Interfaccia ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="ae90f-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="ae90f-103">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="ae90f-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae90f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ae90f-104">Methods</span></span>  
  
|<span data-ttu-id="ae90f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ae90f-105">Method</span></span>|<span data-ttu-id="ae90f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae90f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae90f-107">OpenVirtualProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="ae90f-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="ae90f-108">Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo common language runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="ae90f-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="ae90f-109">CanUnloadNow (metodo)</span><span class="sxs-lookup"><span data-stu-id="ae90f-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="ae90f-110">Determina se una libreria che ha fornita un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia è ancora in uso o può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="ae90f-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae90f-111">Note</span><span class="sxs-lookup"><span data-stu-id="ae90f-111">Remarks</span></span>  
 <span data-ttu-id="ae90f-112">È possibile ottenere un'istanza di `ICLRDebugging` interfaccia utilizzando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ae90f-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae90f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae90f-113">Requirements</span></span>  
 <span data-ttu-id="ae90f-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae90f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae90f-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ae90f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae90f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae90f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae90f-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae90f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae90f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae90f-118">See Also</span></span>  
 [<span data-ttu-id="ae90f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ae90f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ae90f-120">Debug</span><span class="sxs-lookup"><span data-stu-id="ae90f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
