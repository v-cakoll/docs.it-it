---
title: ICorDebugAssembly Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly
helpviewer_keywords: ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d08bb1d2bb7adcbdeb49cd634755d243d34d7f84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="45770-102">ICorDebugAssembly Interface1</span><span class="sxs-lookup"><span data-stu-id="45770-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="45770-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="45770-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45770-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="45770-104">Methods</span></span>  
  
|<span data-ttu-id="45770-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="45770-105">Method</span></span>|<span data-ttu-id="45770-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45770-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45770-107">EnumerateModules (metodo)</span><span class="sxs-lookup"><span data-stu-id="45770-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="45770-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="45770-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="45770-109">GetAppDomain (metodo)</span><span class="sxs-lookup"><span data-stu-id="45770-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="45770-110">Ottiene un puntatore a interfaccia per il dominio applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="45770-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="45770-111">GetCodeBase (metodo)</span><span class="sxs-lookup"><span data-stu-id="45770-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="45770-112">Non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45770-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="45770-113">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="45770-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="45770-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="45770-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="45770-115">GetProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="45770-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="45770-116">Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.</span><span class="sxs-lookup"><span data-stu-id="45770-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45770-117">Note</span><span class="sxs-lookup"><span data-stu-id="45770-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45770-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="45770-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45770-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45770-119">Requirements</span></span>  
 <span data-ttu-id="45770-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45770-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45770-121">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="45770-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45770-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45770-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45770-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45770-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45770-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45770-124">See Also</span></span>  
 [<span data-ttu-id="45770-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="45770-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
