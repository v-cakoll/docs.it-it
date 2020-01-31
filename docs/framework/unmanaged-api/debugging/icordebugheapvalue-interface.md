---
title: Interfaccia ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777583"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="0cb4d-102">Interfaccia ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="0cb4d-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="0cb4d-103">Sottoclasse di "ICorDebugValue" che rappresenta un oggetto raccolto dall'Garbage Collector di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0cb4d-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cb4d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0cb4d-104">Methods</span></span>  
  
|<span data-ttu-id="0cb4d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0cb4d-105">Method</span></span>|<span data-ttu-id="0cb4d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cb4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cb4d-107">Metodo CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0cb4d-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="0cb4d-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0cb4d-108">Not implemented.</span></span>|  
|[<span data-ttu-id="0cb4d-109">Metodo IsValid</span><span class="sxs-lookup"><span data-stu-id="0cb4d-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="0cb4d-110">Ottiene un valore che indica se l'oggetto rappresentato da questo `ICorDebugHeapValue` è valido o è stato recuperato dall'Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="0cb4d-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="0cb4d-111">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="0cb4d-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cb4d-112">Note</span><span class="sxs-lookup"><span data-stu-id="0cb4d-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cb4d-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0cb4d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cb4d-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0cb4d-114">Requirements</span></span>  
 <span data-ttu-id="0cb4d-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cb4d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cb4d-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cb4d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cb4d-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cb4d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cb4d-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb4d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb4d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cb4d-119">See also</span></span>

- [<span data-ttu-id="0cb4d-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0cb4d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
