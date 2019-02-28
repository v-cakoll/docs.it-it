---
title: Interfaccia ICorDebugAssembly
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
ms.openlocfilehash: a2b802845e36e818a962484c1fea09cbcc1ceefd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974575"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="8ebd1-102">Interfaccia ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="8ebd1-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="8ebd1-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ebd1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8ebd1-104">Methods</span></span>  
  
|<span data-ttu-id="8ebd1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8ebd1-105">Method</span></span>|<span data-ttu-id="8ebd1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ebd1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ebd1-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="8ebd1-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="8ebd1-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="8ebd1-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="8ebd1-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="8ebd1-110">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="8ebd1-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="8ebd1-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="8ebd1-112">Non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="8ebd1-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="8ebd1-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="8ebd1-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="8ebd1-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="8ebd1-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="8ebd1-116">Ottiene l'istanza ICorDebugProcess in cui l'assembly è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ebd1-117">Note</span><span class="sxs-lookup"><span data-stu-id="8ebd1-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ebd1-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebd1-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ebd1-119">Requirements</span></span>  
 <span data-ttu-id="8ebd1-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ebd1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebd1-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ebd1-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ebd1-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ebd1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ebd1-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebd1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebd1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ebd1-124">See also</span></span>
- [<span data-ttu-id="8ebd1-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8ebd1-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
