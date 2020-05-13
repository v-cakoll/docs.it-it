---
title: Metodo ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: c83d6e892b89e6e50779abf9a71a2cbe9093af2c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212848"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a>Metodo ICorDebugProcess6::MarkDebuggerAttached
Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fIsAttached`  
 `true` se il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> deve indicare che è collegato un debugger, altrimenti `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo può restituire i valori elencati nella seguente tabella.  
  
|Valore restituito|Description|  
|------------------|-----------------|  
|`S_OK`|L'oggetto del debug è stato aggiornato correttamente.|  
|`CORDBG_E_MODULE_NOT_LOADED`|L'assembly che contiene il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> non è caricato oppure altri errori, ad esempio metadati mancanti, ne stanno impedendo il riconoscimento.<br /><br /> Questo errore è frequente e non grave. Chiamare di nuovo il metodo quando vengono caricati altri assembly.|  
|Altri valori di `HRESULT` con errori.|Altri valori indicano probabilmente il comportamento errato di un debugger o dei componenti del compilatore.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
