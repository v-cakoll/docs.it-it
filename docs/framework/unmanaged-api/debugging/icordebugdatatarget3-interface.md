---
title: Interfaccia ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783494"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="e9a3d-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="e9a3d-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="e9a3d-103">Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="e9a3d-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="e9a3d-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9a3d-104">Method</span></span>  
  
|<span data-ttu-id="e9a3d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9a3d-105">Method</span></span>|<span data-ttu-id="e9a3d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9a3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9a3d-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="e9a3d-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="e9a3d-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="e9a3d-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a3d-109">Note</span><span class="sxs-lookup"><span data-stu-id="e9a3d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9a3d-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e9a3d-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e9a3d-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e9a3d-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9a3d-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e9a3d-112">Requirements</span></span>  
 <span data-ttu-id="e9a3d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a3d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a3d-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9a3d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9a3d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9a3d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9a3d-116">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a3d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a3d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9a3d-117">See also</span></span>

- [<span data-ttu-id="e9a3d-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e9a3d-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e9a3d-119">Debug</span><span class="sxs-lookup"><span data-stu-id="e9a3d-119">Debugging</span></span>](index.md)
