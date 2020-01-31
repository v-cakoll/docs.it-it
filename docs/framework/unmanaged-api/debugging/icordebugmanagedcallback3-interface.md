---
title: Interfaccia ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793278"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="c26c8-102">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="c26c8-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="c26c8-103">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="c26c8-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c26c8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c26c8-104">Methods</span></span>  
  
|<span data-ttu-id="c26c8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c26c8-105">Method</span></span>|<span data-ttu-id="c26c8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c26c8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c26c8-107">Metodo CustomNotification</span><span class="sxs-lookup"><span data-stu-id="c26c8-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="c26c8-108">Indica che è stata generata una notifica del debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="c26c8-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c26c8-109">Note</span><span class="sxs-lookup"><span data-stu-id="c26c8-109">Remarks</span></span>  
 <span data-ttu-id="c26c8-110">Questa interfaccia è un'estensione logica delle interfacce [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c26c8-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c26c8-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c26c8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c26c8-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c26c8-112">Requirements</span></span>  
 <span data-ttu-id="c26c8-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c26c8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c26c8-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c26c8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c26c8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c26c8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c26c8-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c26c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c26c8-117">See also</span></span>

- [<span data-ttu-id="c26c8-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c26c8-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="c26c8-119">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="c26c8-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="c26c8-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c26c8-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c26c8-121">Debug</span><span class="sxs-lookup"><span data-stu-id="c26c8-121">Debugging</span></span>](index.md)
