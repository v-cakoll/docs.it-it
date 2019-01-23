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
ms.openlocfilehash: 4db005e1de043e60ffe958de732a5280fcccbea7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529947"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="fb3bf-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="fb3bf-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="fb3bf-103">Fornisce metodi per recuperare le informazioni associate a un runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="fb3bf-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb3bf-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fb3bf-104">Methods</span></span>  
  
|<span data-ttu-id="fb3bf-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fb3bf-105">Method</span></span>|<span data-ttu-id="fb3bf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb3bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb3bf-107">Metodo GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="fb3bf-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="fb3bf-108">Ottiene i puntatori a interfaccia raw memorizzato nella cache sul RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="fb3bf-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="fb3bf-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="fb3bf-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="fb3bf-110">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato per le maiuscole/minuscole o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="fb3bf-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb3bf-111">Note</span><span class="sxs-lookup"><span data-stu-id="fb3bf-111">Remarks</span></span>  
 <span data-ttu-id="fb3bf-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un oggetto RCW, viene chiamato un debugger `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="fb3bf-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb3bf-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb3bf-113">Requirements</span></span>  
 <span data-ttu-id="fb3bf-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb3bf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb3bf-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb3bf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb3bf-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb3bf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb3bf-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3bf-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb3bf-118">See also</span></span>
- [<span data-ttu-id="fb3bf-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fb3bf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fb3bf-120">Debug</span><span class="sxs-lookup"><span data-stu-id="fb3bf-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
