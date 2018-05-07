---
title: Metodo ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aea837c4973f7a0c157a36c05799536ab528638e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess6markdebuggerattached-method"></a>Metodo ICorDebugProcess6::MarkDebuggerAttached
Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
#### <a name="parameters"></a>Parametri  
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
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
