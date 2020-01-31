---
title: Interfaccia ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 73ef1a64deaf5420246fc1ab3e9f88ba5bf049a5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792228"
---
# <a name="icordebugprocess6-interface"></a>Interfaccia ICorDebugProcess6
Estende logicamente l'interfaccia ICorDebugProcess per abilitare funzionalità come la decodifica degli eventi di debug gestiti, codificati negli eventi di debug per le eccezioni native, e la suddivisione dei moduli virtuali.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DecodeEvent](icordebugprocess6-decodeevent-method.md)|Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.|  
|[Metodo EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md)|Abilita o disabilita la suddivisione dei moduli virtuali.|  
|[Metodo GetCode](icordebugprocess6-getcode-method.md)|Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.|  
|[Metodo GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md)|Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.|  
|[Metodo MarkDebuggerAttached](icordebugprocess6-markdebuggerattached-method.md)|Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.|  
|[Metodo ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)|Notifica a [ICorDebug](icordebug-interface.md) che il processo è in esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
