---
title: Metodo ICorDebugProcess5::GetTypeForTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792333"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>Metodo ICorDebugProcess5::GetTypeForTypeID
Converte un identificatore di tipo in un valore ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 in Identificatore del tipo.  
  
 `ppType`  
 out Puntatore all'indirizzo di un oggetto ICorDebugType.  
  
## <a name="remarks"></a>Note  
 In alcuni casi, i metodi che restituiscono un identificatore di tipo possono restituire un valore null `COR_TYPEID`. Se questo valore viene passato come argomento `id`, il `GetTypeForTypeID` metodo avrà esito negativo e restituirà `E_FAIL`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
