---
title: Metodo ICorDebugILFrame::GetLocalVariable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetLocalVariable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9694ee2e27d8789b661abc7393a480411c2b0191
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="71006-102">Metodo ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="71006-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="71006-103">Ottiene il valore della variabile locale specificata in questo stack frame di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="71006-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71006-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71006-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71006-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71006-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="71006-106">[in] Indice della variabile locale in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="71006-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="71006-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="71006-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71006-108">Note</span><span class="sxs-lookup"><span data-stu-id="71006-108">Remarks</span></span>  
 <span data-ttu-id="71006-109">Il `GetLocalVariable` metodo può essere utilizzato in uno stack frame MSIL o in un frame compilati just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="71006-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71006-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71006-110">Requirements</span></span>  
 <span data-ttu-id="71006-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71006-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71006-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="71006-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71006-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71006-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71006-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71006-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
