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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d17c353d8e2358a1651ba3fbbb1dd718cc681f7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123803"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="a9bfa-102">Metodo ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="a9bfa-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="a9bfa-103">`SetRegisters` non è implementata in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="a9bfa-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a9bfa-104">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a9bfa-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9bfa-105">Usare le operazioni di livello superiore, ad esempio [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oppure [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="a9bfa-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9bfa-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9bfa-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a9bfa-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9bfa-107">Requirements</span></span>  
 <span data-ttu-id="a9bfa-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9bfa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9bfa-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9bfa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9bfa-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9bfa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9bfa-111">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a9bfa-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bfa-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9bfa-112">See also</span></span>

- [<span data-ttu-id="a9bfa-113">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a9bfa-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="a9bfa-114">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a9bfa-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
