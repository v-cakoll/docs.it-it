---
title: ICorDebugILFrame2 Interface1
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
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412435"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="db50e-102">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="db50e-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="db50e-103">Estensione logica dell'interfaccia ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="db50e-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db50e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="db50e-104">Methods</span></span>  
  
|<span data-ttu-id="db50e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="db50e-105">Method</span></span>|<span data-ttu-id="db50e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db50e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db50e-107">Metodo EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="db50e-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="db50e-108">Ottiene un oggetto ICorDebugTypeEnum che contiene il <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="db50e-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="db50e-109">Metodo RemapFunction</span><span class="sxs-lookup"><span data-stu-id="db50e-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="db50e-110">Esegue un nuovo mapping di una funzione modificata specificando il nuovo offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="db50e-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db50e-111">Note</span><span class="sxs-lookup"><span data-stu-id="db50e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db50e-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="db50e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db50e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db50e-113">Requirements</span></span>  
 <span data-ttu-id="db50e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db50e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db50e-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="db50e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db50e-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="db50e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db50e-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db50e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db50e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db50e-118">See Also</span></span>  
 [<span data-ttu-id="db50e-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="db50e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
