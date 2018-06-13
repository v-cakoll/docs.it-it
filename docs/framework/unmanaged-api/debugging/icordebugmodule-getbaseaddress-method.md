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
ms.openlocfilehash: 10e7da7711cd63579589fda416d0d3a4f777eefe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412542"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="6838a-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="6838a-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="6838a-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="6838a-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6838a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6838a-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6838a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6838a-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="6838a-106">[out] Oggetto `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="6838a-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6838a-107">Note</span><span class="sxs-lookup"><span data-stu-id="6838a-107">Remarks</span></span>  
 <span data-ttu-id="6838a-108">Se il modulo è nativo immagine (ovvero, se il modulo è stato generato dal generatore di immagini native, NGen.exe), il relativo indirizzo di base sarà zero.</span><span class="sxs-lookup"><span data-stu-id="6838a-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6838a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6838a-109">Requirements</span></span>  
 <span data-ttu-id="6838a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6838a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6838a-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6838a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6838a-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6838a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6838a-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6838a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6838a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6838a-114">See Also</span></span>  
    
 
