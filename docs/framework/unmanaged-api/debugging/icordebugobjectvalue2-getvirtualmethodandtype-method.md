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
ms.openlocfilehash: 17cb3440c5b33d461b1624608ce115e1942d6beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129712"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a>Metodo ICorDebugObjectValue2::GetVirtualMethodAndType
Questo metodo non è ancora implementato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a>Note  
 Ottiene i puntatori all'interfaccia per le istanze "ICorDebugFunction" e "ICorDebugType" che rappresentano il metodo e il tipo più derivati per il riferimento al membro specificato.  
  
## <a name="see-also"></a>Vedere anche
