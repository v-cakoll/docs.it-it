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
ms.openlocfilehash: f0b9c76ca2c39fcba5a4d0519fc099d0a9d51ec2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721230"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="76e77-102">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="76e77-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="76e77-103">Fornisce un enumeratore che definisce il mapping tra un set di GUID e i relativi tipi corrispondenti che sono rappresentati da istanze di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="76e77-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="76e77-104">Questa interfaccia eredita i metodi dall'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="76e77-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76e77-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="76e77-105">Methods</span></span>  
  
|<span data-ttu-id="76e77-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="76e77-106">Method</span></span>|<span data-ttu-id="76e77-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76e77-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76e77-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="76e77-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="76e77-109">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping alle informazioni sul tipo GUID.</span><span class="sxs-lookup"><span data-stu-id="76e77-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76e77-110">Note</span><span class="sxs-lookup"><span data-stu-id="76e77-110">Remarks</span></span>  
 <span data-ttu-id="76e77-111">Un' `ICorDebugGuidToTypeEnum` oggetto di interfaccia può essere recuperato chiamando il [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="76e77-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="76e77-112">Un debugger può chiamare questa interfaccia [successivo](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) metodo per recuperare [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) gli oggetti che rappresentano i mapping di gestiti rappresentazioni di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi caricati di dominio dell'applicazione utilizzata per la chiamata per il [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="76e77-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e77-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76e77-113">Requirements</span></span>  
 <span data-ttu-id="76e77-114">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e77-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="76e77-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76e77-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76e77-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76e77-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76e77-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e77-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e77-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76e77-118">See also</span></span>
- [<span data-ttu-id="76e77-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="76e77-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
