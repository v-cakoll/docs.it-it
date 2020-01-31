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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784669"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="f8708-102">Interfaccia ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="f8708-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="f8708-103">Rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="f8708-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8708-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8708-104">Methods</span></span>  
  
|<span data-ttu-id="f8708-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f8708-105">Method</span></span>|<span data-ttu-id="f8708-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8708-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8708-107">Metodo EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="f8708-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="f8708-108">Ottiene un enumeratore per i moduli contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8708-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="f8708-109">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="f8708-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="f8708-110">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questa istanza di `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f8708-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="f8708-111">Metodo GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="f8708-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="f8708-112">Non implementato nella versione corrente del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8708-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="f8708-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="f8708-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="f8708-114">Ottiene il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8708-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="f8708-115">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="f8708-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="f8708-116">Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8708-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8708-117">Note</span><span class="sxs-lookup"><span data-stu-id="f8708-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8708-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f8708-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8708-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f8708-119">Requirements</span></span>  
 <span data-ttu-id="f8708-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8708-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8708-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8708-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8708-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8708-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8708-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8708-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8708-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8708-124">See also</span></span>

- [<span data-ttu-id="f8708-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f8708-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
