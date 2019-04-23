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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155714"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="285aa-102">Interfaccia ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="285aa-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="285aa-103">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="285aa-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="285aa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="285aa-104">Methods</span></span>  
  
|<span data-ttu-id="285aa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="285aa-105">Method</span></span>|<span data-ttu-id="285aa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="285aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="285aa-107">Metodo OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="285aa-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="285aa-108">Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo common language runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="285aa-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="285aa-109">Metodo CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="285aa-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="285aa-110">Determina se una libreria che ha fornita un' [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia è ancora in uso o può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="285aa-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="285aa-111">Note</span><span class="sxs-lookup"><span data-stu-id="285aa-111">Remarks</span></span>  
 <span data-ttu-id="285aa-112">È possibile ottenere un'istanza del `ICLRDebugging` interfaccia usando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="285aa-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="285aa-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="285aa-113">Requirements</span></span>  
 <span data-ttu-id="285aa-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="285aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="285aa-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="285aa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="285aa-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="285aa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="285aa-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="285aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285aa-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="285aa-118">See also</span></span>

- [<span data-ttu-id="285aa-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="285aa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="285aa-120">Debug</span><span class="sxs-lookup"><span data-stu-id="285aa-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
