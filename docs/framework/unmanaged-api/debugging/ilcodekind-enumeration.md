---
title: Enumerazione ILCodeKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ILCodeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61fd5ad93c198000556e8e0be3a278a842ab5716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="7d2c9-102">Enumerazione ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="7d2c9-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="7d2c9-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="7d2c9-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7d2c9-104">Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d2c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d2c9-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="7d2c9-106">Membri</span><span class="sxs-lookup"><span data-stu-id="7d2c9-106">Members</span></span>  
  
|<span data-ttu-id="7d2c9-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="7d2c9-107">Member name</span></span>|<span data-ttu-id="7d2c9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d2c9-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="7d2c9-109">Il debugger non ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="7d2c9-110">Il debugger ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d2c9-111">Note</span><span class="sxs-lookup"><span data-stu-id="7d2c9-111">Remarks</span></span>  
 <span data-ttu-id="7d2c9-112">Un membro del `ILCodeKind` enumerazione può essere passato al [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) metodi per determinare se il debugger può accedere a variabili aggiunte nella profiler Strumentazione ReJIT e di ottenere il [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) metodo per determinare se il debugger può accedere al instrumentato.</span><span class="sxs-lookup"><span data-stu-id="7d2c9-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d2c9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d2c9-113">Requirements</span></span>  
 <span data-ttu-id="7d2c9-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d2c9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d2c9-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7d2c9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d2c9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d2c9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d2c9-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d2c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2c9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d2c9-118">See Also</span></span>  
 [<span data-ttu-id="7d2c9-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7d2c9-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="7d2c9-120">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="7d2c9-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="7d2c9-121">ReJIT: Una Guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="7d2c9-121">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
