---
title: Interfaccia ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 57ef9b567d57c77c523ca6daefcf80b1d7de66d1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976408"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="a2de7-102">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="a2de7-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="a2de7-103">Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per fornire informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="a2de7-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="a2de7-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2de7-104">Method</span></span>  
  
|<span data-ttu-id="a2de7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2de7-105">Method</span></span>|<span data-ttu-id="a2de7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2de7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2de7-107">Metodo GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="a2de7-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="a2de7-108">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="a2de7-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2de7-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a2de7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2de7-110">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a2de7-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a2de7-111">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a2de7-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2de7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2de7-112">Requirements</span></span>  
 <span data-ttu-id="a2de7-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2de7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2de7-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2de7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2de7-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2de7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2de7-116">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2de7-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2de7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2de7-117">See also</span></span>

- [<span data-ttu-id="a2de7-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2de7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a2de7-119">Debug</span><span class="sxs-lookup"><span data-stu-id="a2de7-119">Debugging</span></span>](index.md)
