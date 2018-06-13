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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74c5036bdc8a4a75e5711c6dc1d34d8f2c21128f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408671"
---
# <a name="icordebug-interface"></a>Interfaccia ICorDebug
Fornisce metodi che consentono agli sviluppatori di debug delle applicazioni nell'ambiente common language runtime (CLR).  
  
> [!NOTE]
>  Debug in modalità mista (codice gestito e nativo) non è supportato in Windows 95, Windows 98 o Windows ME, o in piattaforme diverse da x86 (ad esempio IA64 e AMD64).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanLaunchOrAttach](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Determina se avviare un nuovo processo o connettersi al processo specificato è possibili all'interno del contesto della configurazione del computer e di runtime corrente.|  
|[Metodo CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Avvia un processo e il relativo thread primario sotto il controllo del debugger.|  
|[Metodo DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Collega il debugger a un processo esistente.|  
|[Metodo EnumerateProcesses](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Ottiene un enumeratore per i processi sottoposti a debug.|  
|[Metodo GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Restituisce l'oggetto "ICorDebugProcess" con l'ID di processo specificato.|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Inizializza il `ICorDebug` oggetto.|  
|[Metodo SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Specifica l'oggetto di gestore eventi per gli eventi gestiti.|  
|[Metodo SetUnmanagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Specifica l'oggetto di gestore eventi per gli eventi non gestiti.|  
|[Metodo Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Termina il `ICorDebug` oggetto.|  
  
## <a name="remarks"></a>Note  
 `ICorDebug` rappresenta un ciclo di elaborazione di eventi per un processo del debugger. Il debugger deve attendere il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback da tutti i processi in fase di debug prima di rilasciare questa interfaccia.  
  
 Il `ICorDebug` oggetto è l'oggetto iniziale per controllare qualsiasi ulteriore debug gestito. Nelle versioni di .NET Framework 1.0 e 1.1, questo oggetto è stato un `CoClass` oggetto creato da COM. In .NET Framework versione 2.0, questo oggetto non è più un `CoClass` oggetto. Deve essere creato per il [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) funzione, che è più compatibile con versione. Questa nuova funzione di creazione consente ai client di ottenere un'implementazione specifica di `ICorDebug`, che emula anche una versione specifica dell'API di debug.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
