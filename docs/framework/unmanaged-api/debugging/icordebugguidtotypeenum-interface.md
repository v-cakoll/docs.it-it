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
ms.openlocfilehash: 91d653587d5b7c35a2a43c7eed7c4bf33e5401f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416751"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="39b8c-102">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="39b8c-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="39b8c-103">Fornisce un enumeratore che definisce il mapping tra un insieme di GUID e i tipi corrispondenti, che sono rappresentati da istanze di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="39b8c-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="39b8c-104">Questa interfaccia eredita i metodi da ICorDebugEnum (interfaccia).</span><span class="sxs-lookup"><span data-stu-id="39b8c-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39b8c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="39b8c-105">Methods</span></span>  
  
|<span data-ttu-id="39b8c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="39b8c-106">Method</span></span>|<span data-ttu-id="39b8c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39b8c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39b8c-108">Icordebugguidtotypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="39b8c-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="39b8c-109">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping di GUID al tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="39b8c-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b8c-110">Note</span><span class="sxs-lookup"><span data-stu-id="39b8c-110">Remarks</span></span>  
 <span data-ttu-id="39b8c-111">Un `ICorDebugGuidToTypeEnum` oggetto di interfaccia può essere recuperato chiamando il [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="39b8c-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="39b8c-112">Un debugger può chiamare questa interfaccia [Avanti](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) metodo per recuperare [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) gestiti di oggetti che rappresentano i mapping di rappresentazioni di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi caricati nel dominio dell'applicazione utilizzata per la chiamata di [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="39b8c-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b8c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39b8c-113">Requirements</span></span>  
 <span data-ttu-id="39b8c-114">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b8c-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="39b8c-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="39b8c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39b8c-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="39b8c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39b8c-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b8c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39b8c-118">See Also</span></span>  
 [<span data-ttu-id="39b8c-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="39b8c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
