---
title: Interfaccia ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b787302902779695c48df6e02e2ee00b28f44cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994110"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="e830d-102">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="e830d-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="e830d-103">Estende logicamente il [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaccia da cui recuperare le informazioni sui simboli di debug aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e830d-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e830d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e830d-104">Methods</span></span>  
  
|<span data-ttu-id="e830d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e830d-105">Method</span></span>|<span data-ttu-id="e830d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e830d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e830d-107">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="e830d-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="e830d-108">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="e830d-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="e830d-109">Metodo GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="e830d-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="e830d-110">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="e830d-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e830d-111">Note</span><span class="sxs-lookup"><span data-stu-id="e830d-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e830d-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e830d-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e830d-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e830d-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e830d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e830d-114">Requirements</span></span>  
 <span data-ttu-id="e830d-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e830d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e830d-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e830d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e830d-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e830d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e830d-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e830d-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e830d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e830d-119">See also</span></span>

- [<span data-ttu-id="e830d-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="e830d-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e830d-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e830d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e830d-122">Debug</span><span class="sxs-lookup"><span data-stu-id="e830d-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
