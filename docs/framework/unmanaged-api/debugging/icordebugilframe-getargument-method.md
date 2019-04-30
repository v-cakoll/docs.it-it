---
title: Metodo ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46852ed8ac53c3a7720edff4833f3dc3cce42bbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995527"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="f7f61-102">Metodo ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="f7f61-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="f7f61-103">Ottiene il valore dell'argomento specificato in questo frame dello stack di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="f7f61-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7f61-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7f61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7f61-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="f7f61-106">[in] L'indice dell'argomento in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="f7f61-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f7f61-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="f7f61-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7f61-108">Note</span><span class="sxs-lookup"><span data-stu-id="f7f61-108">Remarks</span></span>  
 <span data-ttu-id="f7f61-109">Il `GetArgument` metodo può essere utilizzato in uno stack frame MSIL o in un frame compilati just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="f7f61-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f61-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7f61-110">Requirements</span></span>  
 <span data-ttu-id="f7f61-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f61-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f61-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7f61-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7f61-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7f61-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7f61-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f61-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
