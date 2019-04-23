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
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177528"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="a9cc0-102">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="a9cc0-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="a9cc0-103">Fornisce metodi per recuperare informazioni sulle rappresentazioni di gestito di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="a9cc0-104">Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9cc0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a9cc0-105">Methods</span></span>  
  
|<span data-ttu-id="a9cc0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a9cc0-106">Method</span></span>|<span data-ttu-id="a9cc0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9cc0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9cc0-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="a9cc0-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="a9cc0-109">Ottiene un enumeratore per tutte le cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="a9cc0-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="a9cc0-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="a9cc0-111">Ottiene un enumeratore per memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi in un dominio dell'applicazione basati sui rispettivi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9cc0-112">Note</span><span class="sxs-lookup"><span data-stu-id="a9cc0-112">Remarks</span></span>  
 <span data-ttu-id="a9cc0-113">Questa interfaccia deve essere usata da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="a9cc0-114">Quando il metodo recupera gli identificatori di interfaccia supportati da un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server dell'oggetto, il debugger potrebbe usare i metodi definiti in questa interfaccia per eseguirne il mapping a tipi gestiti che corrispondono a tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="a9cc0-115">Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9cc0-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a9cc0-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9cc0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9cc0-117">Requirements</span></span>  
 <span data-ttu-id="a9cc0-118">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9cc0-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="a9cc0-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9cc0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9cc0-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9cc0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9cc0-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9cc0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9cc0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9cc0-122">See also</span></span>

- [<span data-ttu-id="a9cc0-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a9cc0-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
