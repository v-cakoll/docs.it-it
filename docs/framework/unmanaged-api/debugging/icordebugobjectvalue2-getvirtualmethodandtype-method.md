---
title: Metodo ICorDebugObjectValue2::GetVirtualMethodAndType
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 252a65c66764d60f5e307ba1eaad4ded34d9744d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975741"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="b54d2-102">Metodo ICorDebugObjectValue2::GetVirtualMethodAndType</span><span class="sxs-lookup"><span data-stu-id="b54d2-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="b54d2-103">Questo metodo non è ancora implementato.</span><span class="sxs-lookup"><span data-stu-id="b54d2-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b54d2-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b54d2-105">Note</span><span class="sxs-lookup"><span data-stu-id="b54d2-105">Remarks</span></span>  
 <span data-ttu-id="b54d2-106">Ottiene i interfaccia puntatori alle istanze di "ICorDebugFunction" e "ICorDebugType" che rappresentano il metodo più derivata e il tipo per il riferimento al membro specificato.</span><span class="sxs-lookup"><span data-stu-id="b54d2-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54d2-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b54d2-107">See also</span></span>
