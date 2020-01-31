---
title: Metodo ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: b2ecd6da11bffb156826fa0c31b5f32abb54ff4a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792213"
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
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`S_OK`|L'oggetto del debug è stato aggiornato correttamente.|  
|`CORDBG_E_MODULE_NOT_LOADED`|L'assembly che contiene il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> non è caricato oppure altri errori, ad esempio metadati mancanti, ne stanno impedendo il riconoscimento.<br /><br /> Questo errore è frequente e non grave. Chiamare di nuovo il metodo quando vengono caricati altri assembly.|  
|Altri valori di `HRESULT` con errori.|Altri valori indicano probabilmente il comportamento errato di un debugger o dei componenti del compilatore.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
