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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea67c6e4d860d41cfe67aaab73babb51f3ce45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210659"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="69fd1-102">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="69fd1-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="69fd1-103">Fornisce un enumeratore che definisce il mapping tra un set di GUID e i relativi tipi corrispondenti che sono rappresentati da istanze di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="69fd1-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="69fd1-104">Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="69fd1-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69fd1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="69fd1-105">Methods</span></span>  
  
|<span data-ttu-id="69fd1-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="69fd1-106">Method</span></span>|<span data-ttu-id="69fd1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69fd1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69fd1-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="69fd1-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="69fd1-109">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping alle informazioni sul tipo GUID.</span><span class="sxs-lookup"><span data-stu-id="69fd1-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69fd1-110">Note</span><span class="sxs-lookup"><span data-stu-id="69fd1-110">Remarks</span></span>  
 <span data-ttu-id="69fd1-111">Un' `ICorDebugGuidToTypeEnum` oggetto di interfaccia può essere recuperato chiamando il [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="69fd1-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="69fd1-112">Un debugger può chiamare questa interfaccia [successivo](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) metodo per recuperare [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) gli oggetti che rappresentano i mapping di gestiti rappresentazioni di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi caricati di dominio dell'applicazione utilizzata per la chiamata per il [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="69fd1-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69fd1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69fd1-113">Requirements</span></span>  
 **<span data-ttu-id="69fd1-114">Piattaforme:</span><span class="sxs-lookup"><span data-stu-id="69fd1-114">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="69fd1-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69fd1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69fd1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69fd1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="69fd1-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="69fd1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69fd1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69fd1-118">See also</span></span>

- [<span data-ttu-id="69fd1-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="69fd1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
