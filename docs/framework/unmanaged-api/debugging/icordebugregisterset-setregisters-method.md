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
ms.openlocfilehash: 7af3109c822dfe945a60c16d4bd3b764f7550492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131337"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="a17f9-102">Metodo ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="a17f9-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="a17f9-103">`SetRegisters` non è implementato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="a17f9-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a17f9-104">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a17f9-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a17f9-105">Utilizzare le operazioni di livello superiore, ad esempio [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="a17f9-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17f9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a17f9-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a17f9-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a17f9-107">Requirements</span></span>  
 <span data-ttu-id="a17f9-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a17f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17f9-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a17f9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a17f9-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a17f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a17f9-111">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a17f9-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17f9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a17f9-112">See also</span></span>

- [<span data-ttu-id="a17f9-113">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a17f9-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="a17f9-114">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a17f9-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
