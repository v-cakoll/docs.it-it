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
ms.openlocfilehash: 6cf66774209bd07426872c29c15b2225421c2b4d
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396826"
---
# <a name="icordebugvariablehomegetregister-method"></a>Metodo ICorDebugVariableHome:: getRegister
Ottiene il registro contenente una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRegister`  
 out Valore di Enumerazione CorDebugRegister che indica il registro per una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`S_OK`|La variabile si trova nel registro indicato dall' `pRegister` argomento.|  
|`E_FAIL`|La variabile non si trova in un registro o in un percorso relativo al registro.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Enumerazione VariableLocationType](variablelocationtype-enumeration.md)
- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
