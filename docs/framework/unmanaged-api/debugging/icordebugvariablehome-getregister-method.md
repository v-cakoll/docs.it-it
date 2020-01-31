---
title: 'Metodo ICorDebugVariableHome:: getRegister'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790982"
---
# <a name="icordebugvariablehomegetregister-method"></a>Metodo ICorDebugVariableHome:: getRegister
Ottiene il registro contenente una variabile con un tipo di posizione `VLT_REGISTER`e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRegister`  
 out Valore di Enumerazione CorDebugRegister che indica il registro per una variabile con un tipo di posizione `VLT_REGISTER`e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`S_OK`|La variabile si trova nel registro indicato dall'argomento `pRegister`.|  
|`E_FAIL`|La variabile non si trova in un registro o in un percorso relativo al registro.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione VariableLocationType](variablelocationtype-enumeration.md)
- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
