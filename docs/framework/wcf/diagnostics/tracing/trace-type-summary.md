---
title: Riepilogo dei tipi di traccia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486042"
---
# <a name="trace-type-summary"></a>Riepilogo dei tipi di traccia
[SourceLevels](http://go.microsoft.com/fwlink/?LinkID=94943) definisce vari livelli di traccia: critico, errore, avviso, informazioni e dettagliato, nonché come fornisce la descrizione del `ActivityTracing` flag che attiva o disattiva l'output della traccia gli eventi di trasferimento di limite e attività.  
  
 È inoltre possibile rivedere [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) per i tipi di traccia che può essere emessi da <xref:System.Diagnostics>.  
  
 Nella tabella seguente sono elencati quelli più importanti.  
  
|Tipo di traccia|Descrizione|  
|----------------|-----------------|  
|Critical|Errore irreversibile o arresto anomalo dell'applicazione.|  
|Errore|Errore risolvibile.|  
|Avviso|Messaggio informativo.|  
|Informazioni|Problema non critico.|  
|Dettagliato|Traccia di debug.|  
|Inizia|Avvio di un'unità logica di elaborazione.|  
|Sospendi|Sospensione di un'unità logica di elaborazione.|  
|Riprendi|Ripresa di un'unità logica di elaborazione.|  
|Arresta|Interruzione di un'unità logica di elaborazione.|  
|Trasferimento|Modifica dell'identità di correlazione.|  
  
 Un'attività è definita come una combinazione dei tipi di traccia riportati sopra.  
  
 Quella che segue è un'espressione regolare che definisce un'attività ideale in un ambito locale (origine di traccia),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Ciò significa che un'attività deve soddisfare le condizioni seguenti.  
  
-   Deve avviarsi e arrestarsi rispettivamente con tracce Start e Stop.  
  
-   Deve avere una traccia Transfer subito prima di una traccia Suspend o Resume  
  
-   Non deve avere nessuna traccia tra le tracce Suspend e Resume, se esistono  
  
-   Può avere un numero qualsiasi di tracce Critical/Error/Warning/Information/Verbose/Transfer, a condizione che vengano rispettate le condizioni precedenti  
  
 Quella che segue è un'espressione regolare che definisce un'attività ideale in ambito globale,  
  
```  
R+   
```  
  
 con R che è l'espressione regolare per un'attività nell'ambito locale. Ciò si traduce in,  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
