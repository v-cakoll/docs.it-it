---
title: Metodo ICorDebugStringValue::GetLength
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: a6f2f536d360ffe41caf2a96c8b051f9167343c2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138963"
---
# <a name="icordebugstringvaluegetlength-method"></a>Metodo ICorDebugStringValue::GetLength
Ottiene il numero di caratteri nella stringa a cui fa riferimento questo ICorDebugStringValue.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcchString`  
 out Puntatore a un valore che specifica la lunghezza della stringa a cui fa riferimento questo oggetto `ICorDebugStringValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
