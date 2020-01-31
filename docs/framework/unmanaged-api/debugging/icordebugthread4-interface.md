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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791330"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="e9181-102">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="e9181-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="e9181-103">Fornisce informazioni sui blocchi dei thread.</span><span class="sxs-lookup"><span data-stu-id="e9181-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9181-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9181-104">Methods</span></span>  
  
|<span data-ttu-id="e9181-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9181-105">Method</span></span>|<span data-ttu-id="e9181-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9181-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9181-107">Metodo GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="e9181-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="e9181-108">Fornisce un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) che forniscono informazioni di blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="e9181-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="e9181-109">Metodo HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="e9181-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="e9181-110">Indica se il thread ha già avuto un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e9181-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="e9181-111">Metodo GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="e9181-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="e9181-112">Ottiene l'oggetto [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) corrente sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="e9181-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9181-113">Note</span><span class="sxs-lookup"><span data-stu-id="e9181-113">Remarks</span></span>  
 <span data-ttu-id="e9181-114">Questa interfaccia è un'estensione logica delle interfacce ICorDebugThread, ICorDebugThread2 e [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9181-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9181-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e9181-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9181-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e9181-116">Requirements</span></span>  
 <span data-ttu-id="e9181-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9181-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9181-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9181-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9181-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9181-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9181-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9181-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9181-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9181-121">See also</span></span>

- [<span data-ttu-id="e9181-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e9181-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e9181-123">Debug</span><span class="sxs-lookup"><span data-stu-id="e9181-123">Debugging</span></span>](index.md)
