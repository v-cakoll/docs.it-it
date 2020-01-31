---
title: Interfaccia ICorDebug
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: 0ca66f001d04bc86b64e0fe2d1cd37559e4fc633
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785112"
---
# <a name="icordebug-interface"></a>Interfaccia ICorDebug
Fornisce metodi che consentono agli sviluppatori di eseguire il debug di applicazioni nell'ambiente Common Language Runtime (CLR).  
  
> [!NOTE]
> Il debug in modalità mista (codice gestito e nativo) non è supportato in Windows 95, Windows 98 o Windows ME o su piattaforme non x86 (ad esempio IA64 e AMD64).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanLaunchOrAttach](icordebug-canlaunchorattach-method.md)|Determina se è possibile avviare un nuovo processo o connettersi al processo specificato all'interno del contesto della configurazione corrente del computer e del runtime.|  
|[Metodo CreateProcess](icordebug-createprocess-method.md)|Avvia un processo e il relativo thread primario sotto il controllo del debugger.|  
|[Metodo DebugActiveProcess](icordebug-debugactiveprocess-method.md)|Connette il debugger a un processo esistente.|  
|[Metodo EnumerateProcesses](icordebug-enumerateprocesses-method.md)|Ottiene un enumeratore per i processi di cui è in corso il debug.|  
|[Metodo GetProcess](icordebug-getprocess-method.md)|Restituisce l'oggetto "ICorDebugProcess" con l'ID di processo specificato.|  
|[Metodo Initialize](icordebug-initialize-method.md)|Inizializza l'oggetto `ICorDebug`.|  
|[Metodo SetManagedHandler](icordebug-setmanagedhandler-method.md)|Specifica l'oggetto gestore eventi per gli eventi gestiti.|  
|[Metodo SetUnmanagedHandler](icordebug-setunmanagedhandler-method.md)|Specifica l'oggetto gestore eventi per gli eventi non gestiti.|  
|[Metodo Terminate](icordebug-terminate-method.md)|Termina l'oggetto `ICorDebug`.|  
  
## <a name="remarks"></a>Note  
 `ICorDebug` rappresenta un ciclo di elaborazione di eventi per un processo del debugger. Il debugger deve attendere il callback di [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) da tutti i processi di cui è in corso il debug prima di rilasciare questa interfaccia.  
  
 L'oggetto `ICorDebug` è l'oggetto iniziale per controllare tutto il debug gestito ulteriormente. In .NET Framework versioni 1,0 e 1,1, questo oggetto è un oggetto `CoClass` creato da COM. In .NET Framework versione 2,0, questo oggetto non è più un oggetto `CoClass`. Deve essere creato dalla funzione [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , che è più compatibile con la versione. Questa nuova funzione di creazione consente ai client di ottenere un'implementazione specifica di `ICorDebug`, che emula anche una versione specifica dell'API di debug.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
