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
ms.openlocfilehash: 50722bb855c8bc8bcfdc1b405a5bbc2fa057c52c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129525"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="33db6-102">Metodo ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="33db6-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="33db6-103">Ottiene il processo contenitore del modulo.</span><span class="sxs-lookup"><span data-stu-id="33db6-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33db6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33db6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33db6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="33db6-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="33db6-106">out Puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="33db6-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33db6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33db6-107">Requirements</span></span>  
 <span data-ttu-id="33db6-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33db6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33db6-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33db6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33db6-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33db6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33db6-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33db6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
