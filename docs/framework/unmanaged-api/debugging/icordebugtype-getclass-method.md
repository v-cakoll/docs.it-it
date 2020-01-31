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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791302"
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
 out Puntatore all'indirizzo di un'interfaccia `ICorDebugClass` che rappresenta il tipo generico privo di istanze.  
  
## <a name="remarks"></a>Note  
 `GetClass` può essere chiamato solo in determinate condizioni. Chiamare [ICorDebugType:: GetType](icordebugtype-gettype-method.md) prima di chiamare `GetClass`. Se `ICorDebugType::GetType` restituisce un valore CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` può essere chiamato per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
