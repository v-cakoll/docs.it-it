---
title: Interfaccia ICorDebugAppDomain3
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025888"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="5830a-102">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="5830a-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="5830a-103">Fornisce metodi per recuperare informazioni sulle rappresentazioni di tipi Windows Runtime attualmente caricati in un dominio dell'applicazione gestite.</span><span class="sxs-lookup"><span data-stu-id="5830a-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="5830a-104">Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="5830a-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5830a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5830a-105">Methods</span></span>  
  
|<span data-ttu-id="5830a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5830a-106">Method</span></span>|<span data-ttu-id="5830a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5830a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5830a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="5830a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="5830a-109">Ottiene un enumeratore per tutti i tipi Windows Runtime memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="5830a-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="5830a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="5830a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="5830a-111">Ottiene un enumeratore per i tipi Windows Runtime memorizzato nella cache in un dominio di applicazione basato su identificatori relativi interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5830a-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5830a-112">Note</span><span class="sxs-lookup"><span data-stu-id="5830a-112">Remarks</span></span>  
 <span data-ttu-id="5830a-113">Questa interfaccia deve essere usata da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="5830a-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="5830a-114">Quando il metodo recupera gli identificatori di interfaccia supportati da un oggetto server di Windows Runtime, il debugger potrebbe usare i metodi definiti in questa interfaccia per eseguirne il mapping a tipi gestiti che corrispondono a tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="5830a-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="5830a-115">Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="5830a-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5830a-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5830a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5830a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5830a-117">Requirements</span></span>  
 <span data-ttu-id="5830a-118">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="5830a-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="5830a-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5830a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5830a-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5830a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5830a-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5830a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5830a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5830a-122">See also</span></span>

- [<span data-ttu-id="5830a-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5830a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
