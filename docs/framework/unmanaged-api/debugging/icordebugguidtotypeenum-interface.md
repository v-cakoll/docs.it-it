---
title: Interfaccia ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794445"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="209c9-102">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="209c9-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="209c9-103">Fornisce un enumeratore che definisce il mapping tra un set di GUID e i tipi corrispondenti, rappresentati da istanze di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="209c9-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="209c9-104">Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="209c9-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="209c9-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="209c9-105">Methods</span></span>  
  
|<span data-ttu-id="209c9-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="209c9-106">Method</span></span>|<span data-ttu-id="209c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="209c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="209c9-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="209c9-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="209c9-109">Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="209c9-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="209c9-110">Note</span><span class="sxs-lookup"><span data-stu-id="209c9-110">Remarks</span></span>  
 <span data-ttu-id="209c9-111">Un oggetto `ICorDebugGuidToTypeEnum` interfaccia può essere recuperato chiamando il metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="209c9-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="209c9-112">Un debugger può chiamare il metodo [successivo](icordebugguidtotypeenum-next-method.md) di questa interfaccia per recuperare gli oggetti [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che rappresentano i mapping di rappresentazioni gestite dei tipi Windows Runtime caricati nel dominio applicazione usato per la chiamata al metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="209c9-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="209c9-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="209c9-113">Requirements</span></span>  
 <span data-ttu-id="209c9-114">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="209c9-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="209c9-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="209c9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="209c9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="209c9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="209c9-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="209c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209c9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="209c9-118">See also</span></span>

- [<span data-ttu-id="209c9-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="209c9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
