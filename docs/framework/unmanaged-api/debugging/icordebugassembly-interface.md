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
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894905"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="33c30-102">Interfaccia ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="33c30-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="33c30-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="33c30-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33c30-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="33c30-104">Methods</span></span>  
  
|<span data-ttu-id="33c30-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="33c30-105">Method</span></span>|<span data-ttu-id="33c30-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33c30-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33c30-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="33c30-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="33c30-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="33c30-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="33c30-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="33c30-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="33c30-110">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che `ICorDebugAssembly` contiene l'istanza.</span><span class="sxs-lookup"><span data-stu-id="33c30-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="33c30-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="33c30-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="33c30-112">Non implementato nella versione corrente del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33c30-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="33c30-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="33c30-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="33c30-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="33c30-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="33c30-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="33c30-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="33c30-116">Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.</span><span class="sxs-lookup"><span data-stu-id="33c30-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c30-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="33c30-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33c30-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="33c30-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c30-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33c30-119">Requirements</span></span>  
 <span data-ttu-id="33c30-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33c30-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33c30-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33c30-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33c30-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33c30-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33c30-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33c30-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c30-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33c30-124">See also</span></span>

- [<span data-ttu-id="33c30-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="33c30-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
