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
ms.openlocfilehash: a4f57f27ec92e7977b46ebfa5967b0590674d2a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113438"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="2fea1-102">Interfaccia ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="2fea1-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="2fea1-103">Un'estensione logica dell'interfaccia ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="2fea1-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fea1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2fea1-104">Methods</span></span>  
  
|<span data-ttu-id="2fea1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2fea1-105">Method</span></span>|<span data-ttu-id="2fea1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fea1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2fea1-107">Metodo EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="2fea1-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="2fea1-108">Ottiene un oggetto ICorDebugTypeEnum che contiene il <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="2fea1-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="2fea1-109">Metodo RemapFunction</span><span class="sxs-lookup"><span data-stu-id="2fea1-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="2fea1-110">Esegue un nuovo mapping di una funzione modificata specificando il nuovo offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="2fea1-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fea1-111">Note</span><span class="sxs-lookup"><span data-stu-id="2fea1-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fea1-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="2fea1-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fea1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fea1-113">Requirements</span></span>  
 <span data-ttu-id="2fea1-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fea1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fea1-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fea1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fea1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fea1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fea1-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fea1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fea1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fea1-118">See also</span></span>

- [<span data-ttu-id="2fea1-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2fea1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
