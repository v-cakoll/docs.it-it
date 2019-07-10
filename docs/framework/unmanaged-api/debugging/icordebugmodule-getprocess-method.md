---
title: Metodo ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff7c77a27e9be58e9702c3a5e3f990863dc83901
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763630"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="9cbb3-102">Metodo ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="9cbb3-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="9cbb3-103">Ottiene il processo contenitore di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="9cbb3-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cbb3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cbb3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cbb3-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="9cbb3-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo che contiene questo modulo.</span><span class="sxs-lookup"><span data-stu-id="9cbb3-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cbb3-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cbb3-107">Requirements</span></span>  
 <span data-ttu-id="9cbb3-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cbb3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cbb3-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cbb3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cbb3-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cbb3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cbb3-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cbb3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
