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
ms.openlocfilehash: 9270afa1d8c8ddd74cfe6dd05e39c1480f5767e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206939"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="ad424-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="ad424-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="ad424-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="ad424-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad424-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad424-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad424-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad424-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="ad424-106">out Oggetto `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="ad424-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad424-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ad424-107">Remarks</span></span>  
 <span data-ttu-id="ad424-108">Se il modulo è un'immagine nativa, ovvero se il modulo è stato prodotto dal generatore di immagini native, NGen. exe, il relativo indirizzo di base sarà zero.</span><span class="sxs-lookup"><span data-stu-id="ad424-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad424-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad424-109">Requirements</span></span>  
 <span data-ttu-id="ad424-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad424-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad424-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad424-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad424-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad424-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad424-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad424-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad424-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad424-114">See also</span></span>
