---
title: Metodo ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebd36f01297f24c050f84fb67e7673f8641fe206
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475242"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="7bea1-102">Metodo ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="7bea1-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="7bea1-103">Ottiene il valore della variabile locale specificata in questo frame dello stack di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="7bea1-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bea1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bea1-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bea1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7bea1-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="7bea1-106">[in] L'indice della variabile locale in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="7bea1-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="7bea1-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="7bea1-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bea1-108">Note</span><span class="sxs-lookup"><span data-stu-id="7bea1-108">Remarks</span></span>  
 <span data-ttu-id="7bea1-109">Il `GetLocalVariable` metodo può essere utilizzato in uno stack frame MSIL o in un frame compilati just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="7bea1-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bea1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bea1-110">Requirements</span></span>  
 <span data-ttu-id="7bea1-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bea1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bea1-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bea1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bea1-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bea1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bea1-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bea1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
