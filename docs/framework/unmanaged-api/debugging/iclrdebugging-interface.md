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
ms.openlocfilehash: a3d4297e3b16dd1637e6293dbf7f04d4fbeda50f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860392"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="d52ab-102">Interfaccia ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="d52ab-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="d52ab-103">Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.</span><span class="sxs-lookup"><span data-stu-id="d52ab-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d52ab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d52ab-104">Methods</span></span>  
  
|<span data-ttu-id="d52ab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d52ab-105">Method</span></span>|<span data-ttu-id="d52ab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d52ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d52ab-107">Metodo OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="d52ab-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="d52ab-108">Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo Common Language Runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="d52ab-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="d52ab-109">Metodo CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="d52ab-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="d52ab-110">Determina se una libreria fornita da un'interfaccia [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) è ancora in uso o può essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="d52ab-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d52ab-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d52ab-111">Remarks</span></span>  
 <span data-ttu-id="d52ab-112">È possibile ottenere un'istanza dell' `ICLRDebugging` interfaccia tramite la funzione [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d52ab-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52ab-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d52ab-113">Requirements</span></span>  
 <span data-ttu-id="d52ab-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52ab-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d52ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d52ab-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d52ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d52ab-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52ab-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d52ab-118">See also</span></span>

- [<span data-ttu-id="d52ab-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d52ab-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d52ab-120">Debug</span><span class="sxs-lookup"><span data-stu-id="d52ab-120">Debugging</span></span>](index.md)
