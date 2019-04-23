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
ms.openlocfilehash: f213a35a12bfb5cc92558a76e122a1494d567f93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170797"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="3a7a2-102">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3a7a2-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="3a7a2-103">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a7a2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3a7a2-104">Methods</span></span>  
  
|<span data-ttu-id="3a7a2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3a7a2-105">Method</span></span>|<span data-ttu-id="3a7a2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a7a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a7a2-107">Metodo GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="3a7a2-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="3a7a2-108">Fornisce un'enumerazione di ordinato [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture che forniscono le informazioni di blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="3a7a2-109">Metodo HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="3a7a2-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="3a7a2-110">Indica se il thread è stato mai un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="3a7a2-111">Metodo GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="3a7a2-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="3a7a2-112">Ottiene l'oggetto corrente [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) oggetto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a7a2-113">Note</span><span class="sxs-lookup"><span data-stu-id="3a7a2-113">Remarks</span></span>  
 <span data-ttu-id="3a7a2-114">Questa interfaccia è un'estensione logica di ICorDebugThread, ICorDebugThread2, e [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a7a2-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a7a2-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a7a2-116">Requirements</span></span>  
 <span data-ttu-id="3a7a2-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a7a2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7a2-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a7a2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a7a2-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a7a2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a7a2-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7a2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7a2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a7a2-121">See also</span></span>

- [<span data-ttu-id="3a7a2-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3a7a2-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3a7a2-123">Debug</span><span class="sxs-lookup"><span data-stu-id="3a7a2-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
