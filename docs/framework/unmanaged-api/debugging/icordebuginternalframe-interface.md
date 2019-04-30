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
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946380"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="15a3b-102">Interfaccia ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="15a3b-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="15a3b-103">Rappresenta un frame nello stack di runtime interno.</span><span class="sxs-lookup"><span data-stu-id="15a3b-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="15a3b-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="15a3b-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15a3b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="15a3b-105">Methods</span></span>  
  
|<span data-ttu-id="15a3b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="15a3b-106">Method</span></span>|<span data-ttu-id="15a3b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15a3b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15a3b-108">Metodo GetFrameType</span><span class="sxs-lookup"><span data-stu-id="15a3b-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="15a3b-109">Ottiene il tipo di questo frame interno.</span><span class="sxs-lookup"><span data-stu-id="15a3b-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15a3b-110">Note</span><span class="sxs-lookup"><span data-stu-id="15a3b-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15a3b-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="15a3b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a3b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15a3b-112">Requirements</span></span>  
 <span data-ttu-id="15a3b-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a3b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15a3b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15a3b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a3b-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a3b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15a3b-117">See also</span></span>

- [<span data-ttu-id="15a3b-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="15a3b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
