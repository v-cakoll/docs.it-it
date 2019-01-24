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
ms.openlocfilehash: af07df53c094654ab86f5e6531fd78124aded988
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630892"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="3228f-102">Metodo ICorDebugObjectValue2::GetVirtualMethodAndType</span><span class="sxs-lookup"><span data-stu-id="3228f-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="3228f-103">Questo metodo non è ancora implementato.</span><span class="sxs-lookup"><span data-stu-id="3228f-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3228f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3228f-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3228f-105">Note</span><span class="sxs-lookup"><span data-stu-id="3228f-105">Remarks</span></span>  
 <span data-ttu-id="3228f-106">Ottiene i interfaccia puntatori alle istanze di "ICorDebugFunction" e "ICorDebugType" che rappresentano il metodo più derivata e il tipo per il riferimento al membro specificato.</span><span class="sxs-lookup"><span data-stu-id="3228f-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3228f-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3228f-107">See also</span></span>


