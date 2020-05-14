---
title: 'Metodo ICorDebugVariableHome:: GetLocationType'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396567"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a>Metodo ICorDebugVariableHome:: GetLocationType
Ottiene il tipo della posizione nativa della variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pLocationType`  
 out Puntatore al tipo della posizione nativa della variabile.  Per ulteriori informazioni, vedere l'enumerazione [VariableLocationType](variablelocationtype-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Enumerazione VariableLocationType](variablelocationtype-enumeration.md)
