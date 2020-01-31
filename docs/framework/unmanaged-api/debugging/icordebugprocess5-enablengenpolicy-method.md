---
title: Metodo ICorDebugProcess5::EnableNGENPolicy
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792456"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>Metodo ICorDebugProcess5::EnableNGENPolicy
Imposta un valore che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ePolicy`  
 in Costante [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) che determina il modo in cui un'applicazione carica immagini native durante l'esecuzione in un debugger gestito.  
  
## <a name="remarks"></a>Note  
 Se il criterio è impostato correttamente, il metodo restituisce `S_OK`. Se `ePolicy` non è compreso nell'intervallo dei valori enumerati definiti da [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), il metodo restituisce `E_INVALIDARG` e la chiamata al metodo non ha alcun effetto. Se non è possibile aggiornare i criteri del generatore di immagini native (Ngen. exe), il metodo restituisce `E_FAIL`.  
  
 Il metodo `ICorDebugProcess5::EnableNGenPolicy` può essere chiamato in qualsiasi momento durante il ciclo di vita del processo. Il criterio è attivo per tutti i moduli caricati dopo l'impostazione dei criteri.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
