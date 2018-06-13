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
ms.openlocfilehash: 1653913ca7410728f0f90a546f613a9d8b88be7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414053"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="84d30-102">Metodo ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="84d30-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="84d30-103">Ottiene il valore dell'argomento specificato in questo stack frame di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="84d30-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84d30-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84d30-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84d30-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="84d30-106">[in] Indice dell'argomento in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="84d30-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="84d30-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="84d30-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d30-108">Note</span><span class="sxs-lookup"><span data-stu-id="84d30-108">Remarks</span></span>  
 <span data-ttu-id="84d30-109">Il `GetArgument` metodo può essere utilizzato in uno stack frame MSIL o in un frame compilati just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="84d30-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d30-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84d30-110">Requirements</span></span>  
 <span data-ttu-id="84d30-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d30-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d30-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="84d30-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d30-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="84d30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d30-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d30-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
