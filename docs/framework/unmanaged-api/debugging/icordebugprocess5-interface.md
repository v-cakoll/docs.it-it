---
title: Interfaccia ICorDebugProcess5
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a105ca8838820b62e81dae4c0149734339bed7a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620214"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="a5762-102">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="a5762-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="a5762-103">Estende l'interfaccia ICorDebugProcess per supportare l'accesso nell'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti, e per determinare se un debugger carica le immagini dalla cache di immagini native locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5762-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5762-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a5762-104">Methods</span></span>  
  
|<span data-ttu-id="a5762-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a5762-105">Method</span></span>|<span data-ttu-id="a5762-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5762-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5762-107">Metodo EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="a5762-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="a5762-108">Imposta un valore che determina la modalità di caricamento delle immagini native durante l'esecuzione con un debugger gestito in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5762-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="a5762-109">Metodo EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="a5762-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="a5762-110">Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.</span><span class="sxs-lookup"><span data-stu-id="a5762-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="a5762-111">Metodo EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="a5762-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="a5762-112">Ottiene un enumeratore per gli handle di oggetto in un processo.</span><span class="sxs-lookup"><span data-stu-id="a5762-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="a5762-113">Metodo EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="a5762-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="a5762-114">Ottiene un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a5762-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="a5762-115">Metodo EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="a5762-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="a5762-116">Ottiene un enumeratore per le aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a5762-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="a5762-117">Metodo GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="a5762-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="a5762-118">Ottiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="a5762-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="a5762-119">Metodo GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="a5762-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="a5762-120">Ottiene un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) struttura che contiene informazioni sugli oggetti che devono essere sottoposto a garbage collection nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a5762-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="a5762-121">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="a5762-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="a5762-122">Ottiene un puntatore a un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a5762-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="a5762-123">Metodo GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="a5762-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="a5762-124">Ottiene un puntatore a una matrice che contiene informazioni sui campi per un tipo in base al relativo identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="a5762-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="a5762-125">Metodo GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="a5762-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="a5762-126">Ottiene un oggetto di tipo che fornisce informazioni su un oggetto di base relativi agli identificatori di tipo.</span><span class="sxs-lookup"><span data-stu-id="a5762-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="a5762-127">Metodo GetTypeID</span><span class="sxs-lookup"><span data-stu-id="a5762-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="a5762-128">Ottiene l'identificatore di tipo per l'oggetto su un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="a5762-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="a5762-129">Metodo GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="a5762-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="a5762-130">Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="a5762-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5762-131">Note</span><span class="sxs-lookup"><span data-stu-id="a5762-131">Remarks</span></span>  
 <span data-ttu-id="a5762-132">Questa interfaccia estende logicamente l'ICorDebugProcess, ICorDebugProcess2, e [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="a5762-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5762-133">Questa interfaccia supporta la chiamata in modalità remota, da un altro computer o da un altro processo.</span><span class="sxs-lookup"><span data-stu-id="a5762-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5762-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5762-134">Requirements</span></span>  
 <span data-ttu-id="a5762-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5762-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5762-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5762-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5762-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5762-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5762-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5762-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5762-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5762-139">See also</span></span>
- [<span data-ttu-id="a5762-140">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a5762-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a5762-141">Debug</span><span class="sxs-lookup"><span data-stu-id="a5762-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
