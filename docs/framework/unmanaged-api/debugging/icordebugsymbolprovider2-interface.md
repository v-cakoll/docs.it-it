---
title: Interfaccia ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: ca5bb822be515c936560eb4888c72ea306888ff3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791494"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="66611-102">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="66611-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="66611-103">Estende logicamente l'interfaccia [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) per recuperare informazioni aggiuntive sul simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="66611-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66611-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="66611-104">Methods</span></span>  
  
|<span data-ttu-id="66611-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="66611-105">Method</span></span>|<span data-ttu-id="66611-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66611-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66611-107">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="66611-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="66611-108">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="66611-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="66611-109">Metodo GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="66611-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="66611-110">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="66611-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66611-111">Note</span><span class="sxs-lookup"><span data-stu-id="66611-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66611-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66611-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="66611-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="66611-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66611-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="66611-114">Requirements</span></span>  
 <span data-ttu-id="66611-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66611-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66611-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66611-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66611-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66611-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66611-118">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66611-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66611-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66611-119">See also</span></span>

- [<span data-ttu-id="66611-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="66611-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="66611-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="66611-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="66611-122">Debug</span><span class="sxs-lookup"><span data-stu-id="66611-122">Debugging</span></span>](index.md)
