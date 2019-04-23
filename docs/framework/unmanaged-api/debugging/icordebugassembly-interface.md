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
ms.openlocfilehash: 3dd60defc1c003fa4b235ddcb0a78b9a819b1b0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198023"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="33992-102">Interfaccia ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="33992-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="33992-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="33992-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33992-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="33992-104">Methods</span></span>  
  
|<span data-ttu-id="33992-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="33992-105">Method</span></span>|<span data-ttu-id="33992-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33992-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33992-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="33992-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="33992-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="33992-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="33992-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="33992-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="33992-110">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="33992-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="33992-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="33992-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="33992-112">Non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33992-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="33992-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="33992-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="33992-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="33992-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="33992-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="33992-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="33992-116">Ottiene l'istanza ICorDebugProcess in cui l'assembly è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="33992-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33992-117">Note</span><span class="sxs-lookup"><span data-stu-id="33992-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33992-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="33992-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33992-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33992-119">Requirements</span></span>  
 <span data-ttu-id="33992-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33992-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33992-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33992-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33992-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33992-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33992-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33992-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33992-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33992-124">See also</span></span>

- [<span data-ttu-id="33992-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="33992-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
