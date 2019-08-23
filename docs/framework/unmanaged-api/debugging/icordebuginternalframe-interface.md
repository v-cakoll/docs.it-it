---
title: Interfaccia ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9764cdcd07a09f5192a8f43b9baa5be40305c40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910162"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="a5f38-102">Interfaccia ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="a5f38-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="a5f38-103">Rappresenta un frame interno di runtime nello stack.</span><span class="sxs-lookup"><span data-stu-id="a5f38-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="a5f38-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="a5f38-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5f38-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a5f38-105">Methods</span></span>  
  
|<span data-ttu-id="a5f38-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a5f38-106">Method</span></span>|<span data-ttu-id="a5f38-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5f38-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5f38-108">Metodo GetFrameType</span><span class="sxs-lookup"><span data-stu-id="a5f38-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="a5f38-109">Ottiene il tipo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="a5f38-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5f38-110">Note</span><span class="sxs-lookup"><span data-stu-id="a5f38-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5f38-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a5f38-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5f38-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5f38-112">Requirements</span></span>  
 <span data-ttu-id="a5f38-113">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5f38-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5f38-114">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a5f38-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5f38-115">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5f38-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5f38-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5f38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f38-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5f38-117">See also</span></span>

- [<span data-ttu-id="a5f38-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a5f38-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
