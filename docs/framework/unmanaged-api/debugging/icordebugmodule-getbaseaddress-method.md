---
title: Metodo ICorDebugModule::GetBaseAddress
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed6344f9a37d246a551699c94046b8c2b473fd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762686"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="36e53-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="36e53-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="36e53-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="36e53-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36e53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36e53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36e53-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36e53-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="36e53-106">[out] Oggetto `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="36e53-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36e53-107">Note</span><span class="sxs-lookup"><span data-stu-id="36e53-107">Remarks</span></span>  
 <span data-ttu-id="36e53-108">Se il modulo è nativo di immagine (vale a dire, se il modulo è stato prodotto dal generatore di immagini native, NGen.exe), il relativo indirizzo di base sarà pari a zero.</span><span class="sxs-lookup"><span data-stu-id="36e53-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36e53-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36e53-109">Requirements</span></span>  
 <span data-ttu-id="36e53-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36e53-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36e53-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36e53-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36e53-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36e53-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36e53-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36e53-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e53-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36e53-114">See also</span></span>
