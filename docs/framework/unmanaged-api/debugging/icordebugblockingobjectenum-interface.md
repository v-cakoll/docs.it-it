---
title: Interfaccia ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778007"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="4a6b7-102">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="4a6b7-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="4a6b7-103">Fornisce un enumeratore per un elenco di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="4a6b7-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="4a6b7-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="4a6b7-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a6b7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4a6b7-105">Methods</span></span>  
  
|<span data-ttu-id="4a6b7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4a6b7-106">Method</span></span>|<span data-ttu-id="4a6b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a6b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a6b7-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="4a6b7-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="4a6b7-109">Enumera un elenco di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="4a6b7-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a6b7-110">Note</span><span class="sxs-lookup"><span data-stu-id="4a6b7-110">Remarks</span></span>  
 <span data-ttu-id="4a6b7-111">Ogni struttura `CorDebugBlockingObject` rappresenta un oggetto che blocca un thread.</span><span class="sxs-lookup"><span data-stu-id="4a6b7-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a6b7-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4a6b7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6b7-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4a6b7-113">Requirements</span></span>  
 <span data-ttu-id="4a6b7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a6b7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6b7-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a6b7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a6b7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a6b7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a6b7-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6b7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a6b7-118">See also</span></span>

- [<span data-ttu-id="4a6b7-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a6b7-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4a6b7-120">Debug</span><span class="sxs-lookup"><span data-stu-id="4a6b7-120">Debugging</span></span>](index.md)
