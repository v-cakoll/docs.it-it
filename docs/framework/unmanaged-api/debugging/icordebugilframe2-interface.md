---
title: Interfaccia ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917014"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="9147f-102">Interfaccia ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="9147f-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="9147f-103">Estensione logica dell'interfaccia ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="9147f-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9147f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9147f-104">Methods</span></span>  
  
|<span data-ttu-id="9147f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9147f-105">Method</span></span>|<span data-ttu-id="9147f-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9147f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9147f-107">Metodo EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="9147f-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="9147f-108">Ottiene un oggetto ICorDebugTypeEnum che contiene i <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="9147f-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="9147f-109">Metodo RemapFunction</span><span class="sxs-lookup"><span data-stu-id="9147f-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="9147f-110">Consente di rimappare una funzione modificata specificando il nuovo offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="9147f-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9147f-111">Note</span><span class="sxs-lookup"><span data-stu-id="9147f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9147f-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9147f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9147f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9147f-113">Requirements</span></span>  
 <span data-ttu-id="9147f-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9147f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9147f-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9147f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9147f-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9147f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9147f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9147f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9147f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9147f-118">See also</span></span>

- [<span data-ttu-id="9147f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9147f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
