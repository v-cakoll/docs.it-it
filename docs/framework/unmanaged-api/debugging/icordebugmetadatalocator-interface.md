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
ms.openlocfilehash: dd31bf458dde043a04e24251cedcac585fd385f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793034"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="fc624-102">Interfaccia ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="fc624-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="fc624-103">Fornisce informazioni sui metadati al debugger.</span><span class="sxs-lookup"><span data-stu-id="fc624-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc624-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fc624-104">Methods</span></span>  
  
|<span data-ttu-id="fc624-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fc624-105">Method</span></span>|<span data-ttu-id="fc624-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc624-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc624-107">Metodo GetMetaData</span><span class="sxs-lookup"><span data-stu-id="fc624-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="fc624-108">Chiede al debugger di restituire il percorso completo di un modulo i cui metadati sono necessari per completare un'operazione richiesta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="fc624-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc624-109">Note</span><span class="sxs-lookup"><span data-stu-id="fc624-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc624-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fc624-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc624-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fc624-111">Requirements</span></span>  
 <span data-ttu-id="fc624-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc624-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc624-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc624-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc624-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc624-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc624-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc624-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc624-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc624-116">See also</span></span>

- [<span data-ttu-id="fc624-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fc624-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc624-118">Debug</span><span class="sxs-lookup"><span data-stu-id="fc624-118">Debugging</span></span>](index.md)
