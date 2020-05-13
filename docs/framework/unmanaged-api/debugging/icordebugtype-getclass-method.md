---
title: Metodo ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379965"
---
# <a name="icordebugtypegetclass-method"></a>Metodo ICorDebugType::GetClass
Ottiene un puntatore a interfaccia a un ICorDebugClass che rappresenta il tipo generico di cui non è stata creata un'istanza.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppClass`  
 out Puntatore all'indirizzo di un' `ICorDebugClass` interfaccia che rappresenta il tipo generico di cui non è stata creata un'istanza.  
  
## <a name="remarks"></a>Osservazioni  
 `GetClass`può essere chiamato solo in determinate condizioni. Chiamare [ICorDebugType:: GetType](icordebugtype-gettype-method.md) prima di chiamare `GetClass` . Se `ICorDebugType::GetType` restituisce un valore CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` può essere chiamato per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
