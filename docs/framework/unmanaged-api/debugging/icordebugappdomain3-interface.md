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
ms.openlocfilehash: 7c130b92fd5114d067730da3b7cd138d98cf0577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407405"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="c7e53-102">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="c7e53-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="c7e53-103">Fornisce metodi per recuperare le informazioni relative rappresentazioni di gestito di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati in un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7e53-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="c7e53-104">Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="c7e53-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7e53-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c7e53-105">Methods</span></span>  
  
|<span data-ttu-id="c7e53-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c7e53-106">Method</span></span>|<span data-ttu-id="c7e53-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7e53-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7e53-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="c7e53-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="c7e53-109">Ottiene un enumeratore per tutti memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.</span><span class="sxs-lookup"><span data-stu-id="c7e53-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="c7e53-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="c7e53-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="c7e53-111">Ottiene un enumeratore per memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] basato su tipi in un dominio applicazione in base ai relativi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c7e53-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e53-112">Note</span><span class="sxs-lookup"><span data-stu-id="c7e53-112">Remarks</span></span>  
 <span data-ttu-id="c7e53-113">Questa interfaccia è destinata a essere utilizzato da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="c7e53-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="c7e53-114">Quando il metodo recupera gli identificatori di interfaccia supportati da un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] dell'oggetto server, il debugger può utilizzare i metodi definiti in questa interfaccia per eseguirne il mapping di tipi gestiti che corrispondono a tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="c7e53-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="c7e53-115">Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="c7e53-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7e53-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c7e53-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e53-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7e53-117">Requirements</span></span>  
 <span data-ttu-id="c7e53-118">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e53-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="c7e53-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c7e53-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7e53-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c7e53-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7e53-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e53-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e53-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7e53-122">See Also</span></span>  
 [<span data-ttu-id="c7e53-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c7e53-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
