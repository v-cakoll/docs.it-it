---
title: Interfaccia ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 587fc29edce72edca7c811c737d67d96b7cafd27
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955465"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="f2db1-102">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="f2db1-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="f2db1-103">Estende logicamente l'interfaccia [Metodo icordebugsymbolprovider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) per recuperare informazioni aggiuntive sul simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="f2db1-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2db1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f2db1-104">Methods</span></span>  
  
|<span data-ttu-id="f2db1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2db1-105">Method</span></span>|<span data-ttu-id="f2db1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2db1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2db1-107">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="f2db1-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="f2db1-108">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="f2db1-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="f2db1-109">Metodo GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="f2db1-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="f2db1-110">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="f2db1-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2db1-111">Note</span><span class="sxs-lookup"><span data-stu-id="f2db1-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2db1-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2db1-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f2db1-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f2db1-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2db1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2db1-114">Requirements</span></span>  
 <span data-ttu-id="f2db1-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2db1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2db1-116">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2db1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2db1-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2db1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2db1-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2db1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2db1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2db1-119">See also</span></span>

- [<span data-ttu-id="f2db1-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="f2db1-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f2db1-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f2db1-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f2db1-122">Debug</span><span class="sxs-lookup"><span data-stu-id="f2db1-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
