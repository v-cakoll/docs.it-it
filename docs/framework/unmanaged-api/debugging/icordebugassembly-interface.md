---
title: ICorDebugAssembly Interface1
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
ms.openlocfilehash: 88134fb7854091bb60e8084a6d776bdec922c7e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406370"
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="b3a76-102">ICorDebugAssembly Interface1</span><span class="sxs-lookup"><span data-stu-id="b3a76-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="b3a76-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="b3a76-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3a76-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b3a76-104">Methods</span></span>  
  
|<span data-ttu-id="b3a76-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b3a76-105">Method</span></span>|<span data-ttu-id="b3a76-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3a76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3a76-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="b3a76-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="b3a76-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b3a76-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="b3a76-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="b3a76-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="b3a76-110">Ottiene un puntatore a interfaccia per il dominio applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="b3a76-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="b3a76-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="b3a76-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="b3a76-112">Non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3a76-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="b3a76-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="b3a76-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="b3a76-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b3a76-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="b3a76-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="b3a76-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="b3a76-116">Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b3a76-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3a76-117">Note</span><span class="sxs-lookup"><span data-stu-id="b3a76-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3a76-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b3a76-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3a76-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3a76-119">Requirements</span></span>  
 <span data-ttu-id="b3a76-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3a76-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3a76-121">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b3a76-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3a76-122">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b3a76-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3a76-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3a76-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a76-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3a76-124">See Also</span></span>  
 [<span data-ttu-id="b3a76-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b3a76-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
