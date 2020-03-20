---
title: Parole chiave e livelli ETW di CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW keywords
- CLR ETW levels
- ETW, CLR keywords
- ETW, CLR levels
ms.assetid: fdf5856d-516b-4042-849d-911c4518a6cb
ms.openlocfilehash: 2106ed0d85cd116be4d7c46396ad6e1597c4341d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400064"
---
# <a name="clr-etw-keywords-and-levels"></a>Parole chiave e livelli ETW di CLR
Gli eventi Event Tracing for Windows (ETW) possono essere filtrati in base a categoria e livello. Le [Parole chiave ETW di CLR](#clr-etw-keywords) degli eventi permettono di filtrare gli eventi per categoria e vengono usate in diverse combinazioni per i provider di runtime e rundown. I [livelli evento](#etw-event-levels) vengono identificati da flag.  
  
## <a name="clr-etw-keywords"></a>Parole chiave ETW di CLR  
 Le parole chiave sono flag che possono essere combinati per generare valori. In pratica, è possibile usare i valori esadecimali delle parole chiave invece dei nomi delle parole chiave quando si chiamano le utilità della riga di comando.  
  
 Le parole chiave vengono descritte nelle tabelle seguenti.  
  
- [Parole chiave di runtime ETW di CLR](#runtime)  
  
- [Parole chiave rundown ETW CLR](#rundown)  
  
- [Combinazioni di parole chiave per la risoluzione dei simboli per il provider di runtimeKeyword combinations for symbol resolution for the runtime provider](#runtime_combo)  
  
- [Combinazioni di parole chiave per la risoluzione dei simboli per il provider di rundown](#rundown_combo)  
  
<a name="runtime"></a>
### <a name="clr-etw-runtime-keywords"></a>Parole chiave di runtime ETW di CLR  
 La tabella seguente contiene le parole chiave di runtime ETW di CLR, i rispettivi valori e informazioni sullo scopo per cui vengono usate.  
  
|Nome parola chiave di runtime|valore|Scopo|  
|--------------------------|-----------|-------------|  
|`GCKeyword`|0x00000001|Consente la raccolta di [eventi di Garbage Collection](garbage-collection-etw-events.md).|  
|`LoaderKeyword`|0x00000008|Consente la raccolta di [eventi del caricatore](loader-etw-events.md).|  
|`JITKeyword`|0x00000010|Consente la raccolta di [eventi JIT (Just-In-Time)](jit-tracing-etw-events.md).|  
|`NGenKeyword`|0x00000020|Consente la raccolta di eventi per metodi delle immagini native (metodi elaborati dal generatore di immagini native, Ngen.exe). Viene usata con `StartEnumerationKeyword` e `EndEnumerationKeyword`. Questa parola chiave ha un overhead elevato. Genera eventi per ogni metodo incluso in ogni modulo NGen caricato. Se possibile, invece di usare questa parola chiave è consigliabile usare database di programma (PDB) generati da strumenti di profilatura che recuperano informazioni sui metodi dai moduli NGen. Vedere anche `OverrideAndSuppressNGenEventsKeyword` più avanti in questa tabella.|  
|`StartEnumerationKeyword`|0x00000040|Consente l'enumerazione di tutti i metodi nel runtime. Viene usata in combinazione con `NGenKeyword`.|  
|`EndEnumerationKeyword`|0x00000080|Consente l'enumerazione di tutti i metodi eliminati nel runtime. Viene usata in combinazione con `JITKeyword` e `NGenKeyword`.|  
|`SecurityKeyword`|0x00000400|Consente la raccolta di [eventi di sicurezza](security-etw-events.md).|  
|`AppDomainResourceManagementKeyword`|0x00000800|Consente la raccolta di eventi di monitoraggio delle risorse a livello di dominio applicazione.|  
|`JITTracingKeyword`|0x00001000|Consente la raccolta di [eventi di traccia JIT](jit-tracing-etw-events.md).|  
|`InteropKeyword`|0x00002000|Consente la raccolta di [eventi di interoperabilità](interop-etw-events.md).|  
|`ContentionKeyword`|0x00004000|Consente la raccolta di [eventi di conflitto](contention-etw-events.md).|  
|`ExceptionKeyword`|0x00008000|Consente la raccolta di [eventi di eccezione](exception-thrown-v1-etw-event.md).|  
|`ThreadingKeyword`|0x00010000|Consente la raccolta di [eventi del pool di thread](thread-pool-etw-events.md).|  
|`OverrideAndSuppressNGenEventsKeyword`|0x00040000|(Disponibile in .NET Framework 4.5 e versioni successive.) Elimina la parola chiave `NGenKeyword` high-overhead e impedisce la generazione di eventi per i metodi all'interno di moduli NGen. A partire da .NET Framework 4.5.NET Framework 4.5, gli strumenti di profilatura devono utilizzare `OverrideAndSuppressNGenEventsKeyword` e `NGenKeyword` insieme per eliminare la generazione di eventi per i metodi nei moduli NGen. In questo modo, lo strumento di profilatura può usare i più efficienti PDB NGen per ottenere informazioni sui metodi nei moduli NGen. CLR in .NET Framework 4 e versioni precedenti non supporta la creazione di PDB NGen. In queste versioni precedenti CLR non riconosce `OverrideAndSuppressNGenEventsKeyword` ed elabora `NGenKeyword` per generare eventi per i metodi nei moduli NGen.|  
|`PerfTrackKeyWord`|0x2000000|Consente la raccolta di eventi `ModuleLoad` e `ModuleRange` .|  
|`StackKeyword`|0x40000000|Consente la raccolta di [eventi di analisi dello stack](stack-etw-event.md)di CLR.|  
  
<a name="rundown"></a>
### <a name="clr-etw-rundown-keywords"></a>Parole chiave di rundown ETW di CLR  
 La tabella seguente contiene le parole chiave di rundown ETW di CLR, i rispettivi valori e informazioni sullo scopo per cui vengono usate.  
  
|Nome parola chiave di rundown|valore|Scopo|  
|--------------------------|-----------|-------------|  
|`LoaderRundownKeyword`|0x00000008|Consente la raccolta di eventi del caricatore se usata con `StartRundownKeyword` e `EndRundownKeyword`.|  
|`JitRundownKeyword`|0x00000010|Consente la raccolta di eventi `DCStart` e `DCEnd` per metodi compilati tramite JIT se usata con `StartRundownKeyword` e `EndRundownKeyword`.|  
|`NGenRundownKeyword`|0x00000020|Consente la raccolta di eventi `DCStart` e `DCEnd` per metodi delle immagini native NGen se usata con `StartRundownKeyword` e `EndRundownKeyword`. Questa parola chiave ha un overhead elevato. Genera eventi per ogni metodo incluso in ogni modulo NGen caricato. Se possibile, invece di usare questa parola chiave è consigliabile usare database di programma (PDB) generati da strumenti di profilatura che recuperano informazioni sui metodi dai moduli NGen. Vedere anche `OverrideAndSuppressNGenEventsRundownKeyword` più avanti in questa tabella.|  
|`StartRundownKeyword`|0x00000040|Consente l'enumerazione dello stato del sistema durante un rundown di avvio.|  
|`EndRundownKeyword`|0x00000100|Consente l'enumerazione dello stato del sistema durante un rundown di fine.|  
|`AppDomainResourceManagementRundownKeyword`|0x00000800|Consente la raccolta di eventi per il monitoraggio delle risorse a livello di <xref:System.AppDomain> se usata con `StartRundownKeyword` o `EndRundownKeyword`.|  
|`ThreadingKeyword`|0x00010000|Consente la raccolta di eventi del pool di thread.|  
|`OverrideAndSuppressNGenEventsRundownKeyword`|0x00040000|(Disponibile in .NET Framework 4.5 e versioni successive.) Elimina la parola chiave `NGenRundownKeyword` high-overhead e impedisce la generazione di eventi per i metodi all'interno di moduli NGen. A partire da .NET Framework 4.5.NET Framework 4.5, gli strumenti di profilatura devono utilizzare `OverrideAndSuppressNGenEventsRundownKeyword` e `NGenRundownKeyword` insieme per eliminare la generazione di eventi per i metodi nei moduli NGen. In questo modo, lo strumento di profilatura può usare i più efficienti PDB NGen per ottenere informazioni sui metodi nei moduli NGen. CLR in .NET Framework 4 e versioni precedenti non supporta la creazione di PDB NGen. In queste versioni precedenti CLR non riconosce `OverrideAndSuppressNGenEventsRundownKeyword` ed elabora `NGenRundownKeyword` per generare eventi per i metodi nei moduli NGen.|  
|`PerfTrackKeyWord`|0x2000000|Consente la raccolta degli eventi `ModuleDCStart`, `ModuleDCEnd`, `ModuleRangeDCStart`e `ModuleRangeDCEnd` .|
  
<a name="runtime_combo"></a>
### <a name="keyword-combinations-for-symbol-resolution-for-the-runtime-provider"></a>Combinazioni di parole chiave per la risoluzione dei simboli per il provider di runtime  
  
|Parole chiave e flag|Eventi di caricamento/scaricamento di domini applicazione, assembly e moduli|Eventi di caricamento/scaricamento di metodi (tranne gli eventi dinamici)|Eventi dinamici di caricamento/eliminazione di metodi|  
|------------------------|--------------------------------------------------------------|----------------------------------------------------------|-----------------------------------------|  
|`LoaderKeyword`|Eventi di caricamento e scaricamento di moduli.|No.|No.|  
|`JITKeyword`<br /><br /> (+ `StartEnumerationKeyword` non aggiunge nulla)|No.|Eventi di caricamento.|Eventi di caricamento e scaricamento di moduli.|  
|`JITKeyword` +<br /><br /> `EndEnumerationKeyword`|No.|Eventi di caricamento e scaricamento di moduli.|Eventi di caricamento e scaricamento di moduli.|  
|`NGenKeyword`|No.|No.|Non applicabile.|  
|`NGenKeyword` +<br /><br /> `StartEnumerationKeyword`|No.|Eventi di caricamento.|Non applicabile.|  
|`NGenKeyword` +<br /><br /> `EndEnumerationKeyword`|No.|Eventi di scaricamento.|Non applicabile.|  
  
<a name="rundown_combo"></a>
### <a name="keyword-combinations-for-symbol-resolution-for-the-rundown-provider"></a>Combinazioni di parole chiave per la risoluzione dei simboli per il provider di rundown  
  
|Parole chiave e flag|Eventi DCStart/DCEnd di domini applicazione, assembly e moduli|Eventi DCStart/DCEnd di metodi (inclusi gli eventi di metodi dinamici)|  
|------------------------|----------------------------------------------------------------|----------------------------------------------------------------------|  
|`LoaderRundownKeyword` +<br /><br /> `StartRundownKeyword`|Eventi`DCStart` .|No.|  
|`LoaderRundownKeyword` +<br /><br /> `EndRundownKeyword`|Eventi`DCEnd` .|No.|  
|`JITKeyword` +<br /><br /> `StartRundownKeyword`|No.|Eventi`DCStart` .|  
|`JITKeyword` +<br /><br /> `EndRundownKeyword`|No.|Eventi`DCEnd` .|  
|`NGenKeyword` +<br /><br /> `StartRundownKeyword`|No.|Eventi`DCStart` .|  
|`NGenKeyword` +<br /><br /> `EndRundownKeyword`|No.|Eventi`DCEnd` .|  

## <a name="etw-event-levels"></a>Livelli evento ETW  
 Gli eventi ETW possono essere filtrati in base al livello. Se il livello è impostato su 0x5, vengono generati gli eventi di tutti i livelli, inclusi il livello 0x5 e quelli inferiori (ovvero gli eventi che appartengono alle categorie abilitate tramite le parole chiave). Se il livello è impostato su 0x2, vengono generati solo gli eventi che appartengono al livello 0x2 e a quelli inferiori.  
  
 I livelli hanno i significati seguenti:  
  
 0x5 - Dettagliato  
  
 0x4 - Informativo  
  
 0x3 - Avviso  
  
 0x2 - Errore  
  
 0x1 - Critico  
  
 0x0 - LogAlways  
  
## <a name="see-also"></a>Vedere anche

- [Provider ETW di CLR](clr-etw-providers.md)
- [Eventi ETW di CLR](clr-etw-events.md)
- [Eventi ETW in Common Language Runtime](etw-events-in-the-common-language-runtime.md)
