---
title: Metodo ICorDebugRegisterSet::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ee62c903da2f2568884b9be30b22bdcdc2d2c4b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686270"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="7c390-102">Metodo ICorDebugRegisterSet::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="7c390-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="7c390-103">`SetThreadContext` non è implementata in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="7c390-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7c390-104">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7c390-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c390-105">Usare l'operazione di livello superiore [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) per impostare il contesto di un thread.</span><span class="sxs-lookup"><span data-stu-id="7c390-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c390-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c390-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7c390-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c390-107">Requirements</span></span>  
 <span data-ttu-id="7c390-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c390-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c390-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c390-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c390-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c390-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c390-111">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="7c390-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c390-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c390-112">See also</span></span>
- [<span data-ttu-id="7c390-113">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="7c390-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="7c390-114">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="7c390-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
