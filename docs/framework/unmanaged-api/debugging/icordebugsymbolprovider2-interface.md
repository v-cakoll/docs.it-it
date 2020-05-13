---
title: Interfaccia ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379293"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="49a11-102">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="49a11-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="49a11-103">Estende logicamente l'interfaccia [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) per recuperare informazioni aggiuntive sul simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="49a11-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49a11-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49a11-104">Methods</span></span>  
  
|<span data-ttu-id="49a11-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49a11-105">Method</span></span>|<span data-ttu-id="49a11-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49a11-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49a11-107">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="49a11-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="49a11-108">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="49a11-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="49a11-109">Metodo GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="49a11-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="49a11-110">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="49a11-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49a11-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="49a11-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49a11-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="49a11-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="49a11-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="49a11-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a11-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49a11-114">Requirements</span></span>  
 <span data-ttu-id="49a11-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49a11-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a11-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49a11-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49a11-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49a11-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49a11-118">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a11-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a11-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49a11-119">See also</span></span>

- [<span data-ttu-id="49a11-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="49a11-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="49a11-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49a11-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="49a11-122">Debug</span><span class="sxs-lookup"><span data-stu-id="49a11-122">Debugging</span></span>](index.md)
