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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098624"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="8e3c3-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="8e3c3-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="8e3c3-103">Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="8e3c3-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e3c3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8e3c3-104">Methods</span></span>  
  
|<span data-ttu-id="8e3c3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8e3c3-105">Method</span></span>|<span data-ttu-id="8e3c3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e3c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e3c3-107">Metodo GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="8e3c3-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="8e3c3-108">Ottiene i puntatori a interfaccia raw memorizzato nella cache sul RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="8e3c3-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="8e3c3-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="8e3c3-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="8e3c3-110">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato per le maiuscole/minuscole o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="8e3c3-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e3c3-111">Note</span><span class="sxs-lookup"><span data-stu-id="8e3c3-111">Remarks</span></span>  
 <span data-ttu-id="8e3c3-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un oggetto RCW, viene chiamato un debugger `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="8e3c3-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e3c3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e3c3-113">Requirements</span></span>  
 <span data-ttu-id="8e3c3-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e3c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e3c3-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e3c3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e3c3-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e3c3-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8e3c3-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8e3c3-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e3c3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e3c3-118">See also</span></span>

- [<span data-ttu-id="8e3c3-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8e3c3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8e3c3-120">Debug</span><span class="sxs-lookup"><span data-stu-id="8e3c3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
