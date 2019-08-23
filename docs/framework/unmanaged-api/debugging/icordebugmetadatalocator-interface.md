---
title: Interfaccia ICorDebugMetaDataLocator
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cf11ec294486fdc14d424e731eac8e4745d892
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939858"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="2355e-102">Interfaccia ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="2355e-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="2355e-103">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="2355e-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2355e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2355e-104">Methods</span></span>  
  
|<span data-ttu-id="2355e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2355e-105">Method</span></span>|<span data-ttu-id="2355e-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2355e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2355e-107">Metodo GetMetaData</span><span class="sxs-lookup"><span data-stu-id="2355e-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="2355e-108">Chiede al debugger di restituire il percorso completo di un modulo i cui metadati sono necessari per completare un'operazione richiesta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="2355e-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2355e-109">Note</span><span class="sxs-lookup"><span data-stu-id="2355e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2355e-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="2355e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2355e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2355e-111">Requirements</span></span>  
 <span data-ttu-id="2355e-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2355e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2355e-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2355e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2355e-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2355e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2355e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2355e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2355e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2355e-116">See also</span></span>

- [<span data-ttu-id="2355e-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2355e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2355e-118">Debug</span><span class="sxs-lookup"><span data-stu-id="2355e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
