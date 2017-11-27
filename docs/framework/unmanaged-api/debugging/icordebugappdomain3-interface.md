---
title: Interfaccia ICorDebugAppDomain3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3
helpviewer_keywords: ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08f125d7fc388a9b2d31c9cc1cebf2605ffa7e23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="259ea-102">Interfaccia ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="259ea-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="259ea-103">Fornisce metodi per recuperare le informazioni relative rappresentazioni di gestito di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati in un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="259ea-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="259ea-104">Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="259ea-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="259ea-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="259ea-105">Methods</span></span>  
  
|<span data-ttu-id="259ea-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="259ea-106">Method</span></span>|<span data-ttu-id="259ea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="259ea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="259ea-108">Icordebugappdomain3:: Getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="259ea-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="259ea-109">Ottiene un enumeratore per tutti memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.</span><span class="sxs-lookup"><span data-stu-id="259ea-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="259ea-110">Icordebugappdomain3:: Getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="259ea-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="259ea-111">Ottiene un enumeratore per memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] basato su tipi in un dominio applicazione in base ai relativi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="259ea-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="259ea-112">Note</span><span class="sxs-lookup"><span data-stu-id="259ea-112">Remarks</span></span>  
 <span data-ttu-id="259ea-113">Questa interfaccia è destinata a essere utilizzato da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="259ea-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="259ea-114">Quando il metodo recupera gli identificatori di interfaccia supportati da un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] dell'oggetto server, il debugger può utilizzare i metodi definiti in questa interfaccia per eseguirne il mapping di tipi gestiti che corrispondono a tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="259ea-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="259ea-115">Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="259ea-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="259ea-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="259ea-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="259ea-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="259ea-117">Requirements</span></span>  
 <span data-ttu-id="259ea-118">**Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="259ea-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="259ea-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="259ea-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="259ea-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="259ea-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="259ea-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="259ea-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259ea-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="259ea-122">See Also</span></span>  
 [<span data-ttu-id="259ea-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="259ea-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
