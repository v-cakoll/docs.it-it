---
title: Interfaccia ICorDebugComObjectValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugComObjectValue
helpviewer_keywords: ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9adeec14e102ef575f24566980477a285f87ba40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="d6872-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="d6872-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="d6872-103">Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="d6872-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6872-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d6872-104">Methods</span></span>  
  
|<span data-ttu-id="d6872-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d6872-105">Method</span></span>|<span data-ttu-id="d6872-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6872-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6872-107">Metodo GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="d6872-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="d6872-108">Ottiene i puntatori a interfaccia raw memorizzati nella cache su RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="d6872-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="d6872-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="d6872-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="d6872-110">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato in maiuscole per o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="d6872-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6872-111">Note</span><span class="sxs-lookup"><span data-stu-id="d6872-111">Remarks</span></span>  
 <span data-ttu-id="d6872-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un RCW, un debugger chiama `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="d6872-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6872-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6872-113">Requirements</span></span>  
 <span data-ttu-id="d6872-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6872-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6872-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d6872-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6872-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6872-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6872-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6872-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6872-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6872-118">See Also</span></span>  
 [<span data-ttu-id="d6872-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d6872-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d6872-120">Debug</span><span class="sxs-lookup"><span data-stu-id="d6872-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
