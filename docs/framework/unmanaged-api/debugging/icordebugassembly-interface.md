---
title: Interfaccia1 ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6776467eb9f5eaaacadb2908de17fc277e495b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569180"
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="9c115-102">Interfaccia1 ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="9c115-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="9c115-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="9c115-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c115-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9c115-104">Methods</span></span>  
  
|<span data-ttu-id="9c115-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9c115-105">Method</span></span>|<span data-ttu-id="9c115-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c115-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c115-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="9c115-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="9c115-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9c115-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="9c115-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="9c115-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="9c115-110">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="9c115-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="9c115-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="9c115-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="9c115-112">Non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c115-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="9c115-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="9c115-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="9c115-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9c115-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="9c115-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="9c115-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="9c115-116">Ottiene l'istanza ICorDebugProcess in cui l'assembly è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9c115-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c115-117">Note</span><span class="sxs-lookup"><span data-stu-id="9c115-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c115-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9c115-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c115-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c115-119">Requirements</span></span>  
 <span data-ttu-id="9c115-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c115-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c115-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c115-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c115-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c115-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c115-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c115-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c115-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c115-124">See also</span></span>
- [<span data-ttu-id="9c115-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9c115-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
