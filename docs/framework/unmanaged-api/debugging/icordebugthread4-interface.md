---
title: Interfaccia ICorDebugThread4
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf486be306e149e2350e7239884c8f05b84f3a86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422084"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="43373-102">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="43373-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="43373-103">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="43373-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43373-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="43373-104">Methods</span></span>  
  
|<span data-ttu-id="43373-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="43373-105">Method</span></span>|<span data-ttu-id="43373-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43373-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43373-107">Metodo GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="43373-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="43373-108">Fornisce un'enumerazione ordinata di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture che forniscono informazioni di blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="43373-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="43373-109">Metodo HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="43373-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="43373-110">Indica se il thread è già verificata un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="43373-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="43373-111">Metodo GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="43373-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="43373-112">Ottiene l'oggetto corrente [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="43373-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43373-113">Note</span><span class="sxs-lookup"><span data-stu-id="43373-113">Remarks</span></span>  
 <span data-ttu-id="43373-114">Questa interfaccia è un'estensione logica di ICorDebugThread, ICorDebugThread2, e [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="43373-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43373-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="43373-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43373-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43373-116">Requirements</span></span>  
 <span data-ttu-id="43373-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43373-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43373-118">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="43373-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43373-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="43373-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43373-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43373-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43373-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43373-121">See Also</span></span>  
 [<span data-ttu-id="43373-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="43373-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="43373-123">Debug</span><span class="sxs-lookup"><span data-stu-id="43373-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
