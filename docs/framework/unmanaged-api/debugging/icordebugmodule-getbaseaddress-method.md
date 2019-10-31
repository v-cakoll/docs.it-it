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
ms.openlocfilehash: aff8fb0a2316817e413f10e82215556f1f54fbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109631"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="ee711-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="ee711-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="ee711-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="ee711-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee711-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee711-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee711-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee711-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="ee711-106">out `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="ee711-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee711-107">Note</span><span class="sxs-lookup"><span data-stu-id="ee711-107">Remarks</span></span>  
 <span data-ttu-id="ee711-108">Se il modulo è un'immagine nativa, ovvero se il modulo è stato prodotto dal generatore di immagini native, NGen. exe, il relativo indirizzo di base sarà zero.</span><span class="sxs-lookup"><span data-stu-id="ee711-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee711-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee711-109">Requirements</span></span>  
 <span data-ttu-id="ee711-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee711-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee711-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee711-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee711-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee711-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee711-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee711-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee711-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee711-114">See also</span></span>
