---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782924"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a>Metodo ICorDebugExceptionDebugEvent::GetFlags
Ottiene un flag che indica se è possibile intercettare l'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwFlags`  
 out Puntatore a un valore [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) che indica se l'eccezione può essere intercettata.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
