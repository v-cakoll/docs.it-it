---
title: Interfaccia ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 6506b11d97490f796486729dbeb612e47762b60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111442"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="d2bbe-102">Interfaccia ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="d2bbe-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="d2bbe-103">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="d2bbe-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2bbe-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d2bbe-104">Methods</span></span>  
  
|<span data-ttu-id="d2bbe-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d2bbe-105">Method</span></span>|<span data-ttu-id="d2bbe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2bbe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2bbe-107">Metodo OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="d2bbe-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="d2bbe-108">Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo Common Language Runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="d2bbe-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="d2bbe-109">Metodo CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="d2bbe-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="d2bbe-110">Determina se una libreria fornita da un'interfaccia [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) è ancora in uso o può essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="d2bbe-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2bbe-111">Note</span><span class="sxs-lookup"><span data-stu-id="d2bbe-111">Remarks</span></span>  
 <span data-ttu-id="d2bbe-112">È possibile ottenere un'istanza dell'interfaccia `ICLRDebugging` tramite la funzione [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d2bbe-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2bbe-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2bbe-113">Requirements</span></span>  
 <span data-ttu-id="d2bbe-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2bbe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2bbe-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2bbe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2bbe-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2bbe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2bbe-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2bbe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bbe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2bbe-118">See also</span></span>

- [<span data-ttu-id="d2bbe-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d2bbe-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d2bbe-120">Debug</span><span class="sxs-lookup"><span data-stu-id="d2bbe-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
