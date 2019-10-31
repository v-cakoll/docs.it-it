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
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138525"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="13098-102">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="13098-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="13098-103">Fornisce un enumeratore che definisce il mapping tra un set di GUID e i tipi corrispondenti, rappresentati da istanze di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="13098-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="13098-104">Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="13098-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13098-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="13098-105">Methods</span></span>  
  
|<span data-ttu-id="13098-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="13098-106">Method</span></span>|<span data-ttu-id="13098-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13098-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13098-108">ICorDebugGuidToTypeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="13098-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="13098-109">Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="13098-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13098-110">Note</span><span class="sxs-lookup"><span data-stu-id="13098-110">Remarks</span></span>  
 <span data-ttu-id="13098-111">Un oggetto `ICorDebugGuidToTypeEnum` interfaccia può essere recuperato chiamando il metodo [ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13098-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="13098-112">Un debugger può chiamare il metodo [successivo](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) di questa interfaccia per recuperare gli oggetti [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che rappresentano i mapping di rappresentazioni gestite dei tipi Windows Runtime caricati nel dominio applicazione usato per la chiamata al [Metodo Metodo ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13098-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13098-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13098-113">Requirements</span></span>  
 <span data-ttu-id="13098-114">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="13098-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="13098-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13098-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13098-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13098-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13098-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13098-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13098-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13098-118">See also</span></span>

- [<span data-ttu-id="13098-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="13098-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
