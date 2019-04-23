---
title: Interfaccia ICorDebugComObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098624"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="3b175-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="3b175-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="3b175-103">Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="3b175-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b175-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3b175-104">Methods</span></span>  
  
|<span data-ttu-id="3b175-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3b175-105">Method</span></span>|<span data-ttu-id="3b175-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b175-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b175-107">Metodo GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="3b175-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="3b175-108">Ottiene i puntatori a interfaccia raw memorizzato nella cache sul RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="3b175-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="3b175-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="3b175-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="3b175-110">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato per le maiuscole/minuscole o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="3b175-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b175-111">Note</span><span class="sxs-lookup"><span data-stu-id="3b175-111">Remarks</span></span>  
 <span data-ttu-id="3b175-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un oggetto RCW, viene chiamato un debugger `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="3b175-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b175-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b175-113">Requirements</span></span>  
 <span data-ttu-id="3b175-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b175-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b175-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b175-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b175-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b175-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b175-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b175-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b175-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b175-118">See also</span></span>

- [<span data-ttu-id="3b175-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3b175-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3b175-120">Debug</span><span class="sxs-lookup"><span data-stu-id="3b175-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
