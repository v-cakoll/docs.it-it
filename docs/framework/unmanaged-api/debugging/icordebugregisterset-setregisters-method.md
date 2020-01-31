---
title: Metodo ICorDebugRegisterSet::SetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: d61d37448930d451b519c93909165e5e16f92765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792047"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="a013c-102">Metodo ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="a013c-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="a013c-103">`SetRegisters` non è implementato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="a013c-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a013c-104">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a013c-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a013c-105">Utilizzare le operazioni di livello superiore, ad esempio [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="a013c-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a013c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a013c-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a013c-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a013c-107">Requirements</span></span>  
 <span data-ttu-id="a013c-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a013c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a013c-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a013c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a013c-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a013c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a013c-111">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a013c-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a013c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a013c-112">See also</span></span>

- [<span data-ttu-id="a013c-113">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a013c-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="a013c-114">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a013c-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
