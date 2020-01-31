---
title: ICorDebugAppDomain3 Interface
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
ms.openlocfilehash: 1aaccb37ec61ed1ba6a7e6e1f508704973117cca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784876"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="b8a85-102">ICorDebugAppDomain3 Interface</span><span class="sxs-lookup"><span data-stu-id="b8a85-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="b8a85-103">Fornisce metodi per recuperare informazioni sulle rappresentazioni gestite dei tipi Windows Runtime attualmente caricati in un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8a85-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="b8a85-104">Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="b8a85-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8a85-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b8a85-105">Methods</span></span>  
  
|<span data-ttu-id="b8a85-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b8a85-106">Method</span></span>|<span data-ttu-id="b8a85-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8a85-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8a85-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="b8a85-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="b8a85-109">Ottiene un enumeratore per tutti i tipi di Windows Runtime memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="b8a85-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="b8a85-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="b8a85-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="b8a85-111">Ottiene un enumeratore per i tipi di Windows Runtime memorizzati nella cache in un dominio applicazione in base ai relativi identificatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b8a85-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8a85-112">Note</span><span class="sxs-lookup"><span data-stu-id="b8a85-112">Remarks</span></span>  
 <span data-ttu-id="b8a85-113">Questa interfaccia deve essere utilizzata da un debugger insieme a una chiamata di valutazione della funzione per `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="b8a85-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="b8a85-114">Quando il metodo recupera gli identificatori di interfaccia supportati da un oggetto Windows Runtime Server, il debugger può utilizzare i metodi definiti in questa interfaccia per eseguirne il mapping ai tipi gestiti che corrispondono a tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="b8a85-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="b8a85-115">Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="b8a85-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8a85-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b8a85-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a85-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b8a85-117">Requirements</span></span>  
 <span data-ttu-id="b8a85-118">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="b8a85-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="b8a85-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8a85-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8a85-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8a85-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a85-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a85-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a85-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8a85-122">See also</span></span>

- [<span data-ttu-id="b8a85-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b8a85-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
