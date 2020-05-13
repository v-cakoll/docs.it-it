---
title: Metodo ICorDebugType::GetFirstTypeParameter
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: da0097daea183c76f97f0b1966b313e1cb5a557b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379944"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a>Metodo ICorDebugType::GetFirstTypeParameter
Ottiene un puntatore a interfaccia a un oggetto ICorDebugType che rappresenta il primo <xref:System.Type> parametro del tipo rappresentato da questo oggetto `ICorDebugType` .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `value`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il primo parametro.  
  
## <a name="remarks"></a>Osservazioni  
 `GetFirstTypeParameter`può essere chiamato nei casi in cui le informazioni aggiuntive sul tipo includono al massimo un parametro di tipo. In particolare, può essere utilizzata se il tipo è un ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR, come indicato dal metodo [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
