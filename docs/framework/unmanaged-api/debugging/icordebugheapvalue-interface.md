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
ms.openlocfilehash: 36a485413490045ca49b99fca4fe5d43edc37114
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213010"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="38aa4-102">Interfaccia ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="38aa4-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="38aa4-103">Sottoclasse di "ICorDebugValue" che rappresenta un oggetto raccolto dall'Garbage Collector di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="38aa4-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38aa4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="38aa4-104">Methods</span></span>  
  
|<span data-ttu-id="38aa4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="38aa4-105">Method</span></span>|<span data-ttu-id="38aa4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38aa4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38aa4-107">Metodo CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="38aa4-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="38aa4-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="38aa4-108">Not implemented.</span></span>|  
|[<span data-ttu-id="38aa4-109">Metodo IsValid</span><span class="sxs-lookup"><span data-stu-id="38aa4-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="38aa4-110">Ottiene un valore che indica se l'oggetto rappresentato da `ICorDebugHeapValue` è valido o è stato recuperato dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="38aa4-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="38aa4-111">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="38aa4-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38aa4-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="38aa4-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38aa4-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="38aa4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38aa4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38aa4-114">Requirements</span></span>  
 <span data-ttu-id="38aa4-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38aa4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38aa4-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38aa4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38aa4-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38aa4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38aa4-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38aa4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38aa4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38aa4-119">See also</span></span>

- [<span data-ttu-id="38aa4-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="38aa4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
