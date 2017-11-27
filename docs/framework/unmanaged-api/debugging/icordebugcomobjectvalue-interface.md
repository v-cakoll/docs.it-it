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
ms.openlocfilehash: 8d339d3146a8a9214c3518eac6c31ed5222f9b31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="a125c-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="a125c-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="a125c-103">Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="a125c-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a125c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a125c-104">Methods</span></span>  
  
|<span data-ttu-id="a125c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a125c-105">Method</span></span>|<span data-ttu-id="a125c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a125c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a125c-107">GetCachedInterfacePointers (metodo)</span><span class="sxs-lookup"><span data-stu-id="a125c-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="a125c-108">Ottiene i puntatori a interfaccia raw memorizzati nella cache su RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="a125c-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="a125c-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="a125c-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="a125c-110">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato in maiuscole per o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="a125c-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a125c-111">Note</span><span class="sxs-lookup"><span data-stu-id="a125c-111">Remarks</span></span>  
 <span data-ttu-id="a125c-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un RCW, un debugger chiama `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="a125c-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a125c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a125c-113">Requirements</span></span>  
 <span data-ttu-id="a125c-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a125c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a125c-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a125c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a125c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a125c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a125c-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a125c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a125c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a125c-118">See Also</span></span>  
 [<span data-ttu-id="a125c-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a125c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a125c-120">Debug</span><span class="sxs-lookup"><span data-stu-id="a125c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
