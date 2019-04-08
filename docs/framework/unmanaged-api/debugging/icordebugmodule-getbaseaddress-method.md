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
ms.openlocfilehash: 763f2872099fac87138b7e1ab058c60475892b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107419"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="adc15-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="adc15-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="adc15-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="adc15-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adc15-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adc15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="adc15-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="adc15-106">[out] Oggetto `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="adc15-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adc15-107">Note</span><span class="sxs-lookup"><span data-stu-id="adc15-107">Remarks</span></span>  
 <span data-ttu-id="adc15-108">Se il modulo è nativo di immagine (vale a dire, se il modulo è stato prodotto dal generatore di immagini native, NGen.exe), il relativo indirizzo di base sarà pari a zero.</span><span class="sxs-lookup"><span data-stu-id="adc15-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc15-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="adc15-109">Requirements</span></span>  
 <span data-ttu-id="adc15-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adc15-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc15-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adc15-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adc15-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adc15-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="adc15-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="adc15-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="adc15-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adc15-114">See also</span></span>
