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
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423371"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="58552-102">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="58552-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="58552-103">Estende l'interfaccia ICorDebugProcess per supportare l'accesso all'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti, e per determinare se un debugger carica le immagini dalla cache delle immagini native locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58552-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58552-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="58552-104">Methods</span></span>  
  
|<span data-ttu-id="58552-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="58552-105">Method</span></span>|<span data-ttu-id="58552-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58552-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58552-107">Metodo EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="58552-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="58552-108">Imposta un valore che determina come un'applicazione carica le immagini native durante l'esecuzione in un debugger gestito.</span><span class="sxs-lookup"><span data-stu-id="58552-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="58552-109">Metodo EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="58552-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="58552-110">Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.</span><span class="sxs-lookup"><span data-stu-id="58552-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="58552-111">Metodo EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="58552-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="58552-112">Ottiene un enumeratore per gli handle di oggetto in un processo.</span><span class="sxs-lookup"><span data-stu-id="58552-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="58552-113">Metodo EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="58552-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="58552-114">Ottiene un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="58552-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="58552-115">Metodo EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="58552-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="58552-116">Ottiene un enumeratore per le aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="58552-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="58552-117">Metodo GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="58552-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="58552-118">Ottiene informazioni sul layout di una matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="58552-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="58552-119">Metodo GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="58552-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="58552-120">Ottiene un puntatore a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) struttura che contiene informazioni sugli oggetti che devono essere sottoposto a garbage collection nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="58552-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="58552-121">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="58552-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="58552-122">Ottiene un puntatore a un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="58552-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="58552-123">Metodo GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="58552-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="58552-124">Ottiene un puntatore a una matrice che contiene informazioni sui campi per un tipo in base al relativo identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="58552-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="58552-125">Metodo GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="58552-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="58552-126">Ottiene un oggetto di tipo che fornisce informazioni su un oggetto in base ai relativi identificatori di tipo.</span><span class="sxs-lookup"><span data-stu-id="58552-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="58552-127">Metodo GetTypeID</span><span class="sxs-lookup"><span data-stu-id="58552-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="58552-128">Ottiene l'identificatore di tipo per l'oggetto a un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="58552-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="58552-129">Metodo GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="58552-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="58552-130">Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="58552-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58552-131">Note</span><span class="sxs-lookup"><span data-stu-id="58552-131">Remarks</span></span>  
 <span data-ttu-id="58552-132">Questa interfaccia estende logicamente l'ICorDebugProcess, ICorDebugProcess2, e [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="58552-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58552-133">Questa interfaccia non supporta la chiamata in modalità remota, da un altro computer o da un altro processo.</span><span class="sxs-lookup"><span data-stu-id="58552-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58552-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58552-134">Requirements</span></span>  
 <span data-ttu-id="58552-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58552-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58552-136">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="58552-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58552-137">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="58552-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58552-138">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58552-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58552-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58552-139">See Also</span></span>  
 [<span data-ttu-id="58552-140">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="58552-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="58552-141">Debug</span><span class="sxs-lookup"><span data-stu-id="58552-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
