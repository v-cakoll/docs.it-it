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
ms.openlocfilehash: 4e9b9221aa2f5e048a94c225660ba2ac9214549c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108830"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="2ed06-102">Interfaccia ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="2ed06-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="2ed06-103">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="2ed06-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ed06-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2ed06-104">Methods</span></span>  
  
|<span data-ttu-id="2ed06-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2ed06-105">Method</span></span>|<span data-ttu-id="2ed06-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ed06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ed06-107">Metodo GetMetaData</span><span class="sxs-lookup"><span data-stu-id="2ed06-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="2ed06-108">Chiede al debugger di restituire il percorso completo di un modulo i cui metadati sono necessari per completare un'operazione richiesta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="2ed06-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ed06-109">Note</span><span class="sxs-lookup"><span data-stu-id="2ed06-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ed06-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="2ed06-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed06-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ed06-111">Requirements</span></span>  
 <span data-ttu-id="2ed06-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ed06-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed06-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ed06-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ed06-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ed06-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2ed06-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ed06-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ed06-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ed06-116">See also</span></span>

- [<span data-ttu-id="2ed06-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2ed06-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2ed06-118">Debug</span><span class="sxs-lookup"><span data-stu-id="2ed06-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
