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
ms.openlocfilehash: 0586b9e184a0958b978837601db002e035881cbc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421033"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="fc16e-102">Enumerazione ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="fc16e-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="fc16e-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="fc16e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fc16e-104">Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="fc16e-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc16e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc16e-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="fc16e-106">Membri</span><span class="sxs-lookup"><span data-stu-id="fc16e-106">Members</span></span>  
  
|<span data-ttu-id="fc16e-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="fc16e-107">Member name</span></span>|<span data-ttu-id="fc16e-108">Description</span><span class="sxs-lookup"><span data-stu-id="fc16e-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="fc16e-109">Il debugger non ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="fc16e-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="fc16e-110">Il debugger ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="fc16e-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc16e-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fc16e-111">Remarks</span></span>  
 <span data-ttu-id="fc16e-112">Un membro dell' `ILCodeKind` enumerazione può essere passato ai metodi [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) per determinare se il debugger può accedere a variabili aggiunte nella strumentazione ReJIT del profiler e al metodo [GetCodeEx](icordebugilframe4-getcodeex-method.md) per determinare se il debugger può accedere al linguaggio il instrumentato.</span><span class="sxs-lookup"><span data-stu-id="fc16e-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc16e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc16e-113">Requirements</span></span>  
 <span data-ttu-id="fc16e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc16e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc16e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc16e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc16e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc16e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc16e-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc16e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc16e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc16e-118">See also</span></span>

- [<span data-ttu-id="fc16e-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="fc16e-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="fc16e-120">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="fc16e-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="fc16e-121">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="fc16e-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
