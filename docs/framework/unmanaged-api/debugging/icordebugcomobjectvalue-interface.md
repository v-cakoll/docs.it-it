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
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892814"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="6a7e0-102">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="6a7e0-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="6a7e0-103">Fornisce metodi per recuperare le informazioni associate a un Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="6a7e0-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a7e0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6a7e0-104">Methods</span></span>  
  
|<span data-ttu-id="6a7e0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6a7e0-105">Method</span></span>|<span data-ttu-id="6a7e0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a7e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a7e0-107">Metodo GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="6a7e0-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="6a7e0-108">Ottiene i puntatori dell'interfaccia raw memorizzati nella cache dell'RCW corrente.</span><span class="sxs-lookup"><span data-stu-id="6a7e0-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="6a7e0-109">Metodo GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="6a7e0-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="6a7e0-110">Fornisce un enumeratore per i tipi di interfaccia a cui è stato assegnato o utilizzato l'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="6a7e0-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a7e0-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6a7e0-111">Remarks</span></span>  
 <span data-ttu-id="6a7e0-112">Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un RCW, un debugger chiama `QueryInterface` "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="6a7e0-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a7e0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a7e0-113">Requirements</span></span>  
 <span data-ttu-id="6a7e0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a7e0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a7e0-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a7e0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a7e0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a7e0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a7e0-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a7e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7e0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a7e0-118">See also</span></span>

- [<span data-ttu-id="6a7e0-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6a7e0-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6a7e0-120">Debug</span><span class="sxs-lookup"><span data-stu-id="6a7e0-120">Debugging</span></span>](index.md)
