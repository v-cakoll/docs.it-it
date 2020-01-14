---
title: Enumerazione ILCodeKind
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937831"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="0c3c7-102">Enumerazione ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="0c3c7-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="0c3c7-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="0c3c7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0c3c7-104">Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="0c3c7-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3c7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c3c7-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="0c3c7-106">Membri</span><span class="sxs-lookup"><span data-stu-id="0c3c7-106">Members</span></span>  
  
|<span data-ttu-id="0c3c7-107">Nome membro</span><span class="sxs-lookup"><span data-stu-id="0c3c7-107">Member name</span></span>|<span data-ttu-id="0c3c7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c3c7-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="0c3c7-109">Il debugger non ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0c3c7-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="0c3c7-110">Il debugger ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0c3c7-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c3c7-111">Note</span><span class="sxs-lookup"><span data-stu-id="0c3c7-111">Remarks</span></span>  
 <span data-ttu-id="0c3c7-112">Un membro dell'enumerazione `ILCodeKind` può essere passato ai metodi [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) per determinare se il debugger può accedere a variabili aggiunte nella strumentazione ReJIT del profiler e al metodo [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) per determinare se IL debugger può accedere al linguaggio il instrumentato.</span><span class="sxs-lookup"><span data-stu-id="0c3c7-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c3c7-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0c3c7-113">Requirements</span></span>  
 <span data-ttu-id="0c3c7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c3c7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c3c7-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c3c7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c3c7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c3c7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c3c7-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c3c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c3c7-118">See also</span></span>

- [<span data-ttu-id="0c3c7-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="0c3c7-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="0c3c7-120">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="0c3c7-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="0c3c7-121">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="0c3c7-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
