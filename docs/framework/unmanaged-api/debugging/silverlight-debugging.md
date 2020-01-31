---
title: Debug Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 91f311818b615ea8f166bb3362ec52d39fcd0297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790318"
---
# <a name="silverlight-debugging"></a>Debug Silverlight
Gli argomenti in questa sezione descrivono l'ambiente e le interfacce forniti da Common Language Runtime (CLR) per supportare il debug delle applicazioni basate su Silverlight in esecuzione nel sistema operativo Windows o sulla piattaforma Macintosh.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione EnumerateCLRs](enumerateclrs-function.md)  
 Fornisce un meccanismo per l'enumerazione di CLR in un processo.  
  
 [Funzione CloseCLREnumeration](closeclrenumeration-function.md)  
 Chiude tutti gli eventi di avvio continuo di CLR validi presenti in una matrice di handle restituiti dalla [funzione EnumerateCLRs](enumerateclrs-function.md)e libera la memoria per le matrici del percorso di stringa e di handle.  
  
 [Funzione CreateCoreClrDebugTarget](createcoreclrdebugtarget-function.md)  
 Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione CreateCordbObject](createcordbobject-function.md)  
 Crea un'interfaccia del debugger che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.  
  
 [Funzione CreateVersionStringFromModule](createversionstringfrommodule-function.md)  
 Crea una stringa di versione da un percorso CLR in un processo di destinazione.  
  
 [Funzione CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function-for-silverlight.md)  
 Accetta una stringa di versione CLR restituita dalla funzione [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)e restituisce un'interfaccia del debugger corrispondente.  
  
 [Struttura CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)  
 Rappresenta un processo in esecuzione in un computer remoto.  
  
 [Struttura CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md)  
 Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.  
  
 [Funzione GetStartupNotificationEvent](getstartupnotificationevent-function.md)  
 Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.  
  
 [Interfaccia ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)  
 Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione InitDbgTransportManager](initdbgtransportmanager-function.md)  
 Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
 [Funzione ShutdownDbgTransportManager](shutdowndbgtransportmanager-function.md)  
 Arresta il gestore trasporto per una connessione a un computer di destinazione remoto.  
  
## <a name="see-also"></a>Vedere anche

- [Coclassi di debug](debugging-coclasses.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Funzioni statiche globali di debug](debugging-global-static-functions.md)
- [Enumerazioni di debug](debugging-enumerations.md)
- [Strutture di debug](debugging-structures.md)
