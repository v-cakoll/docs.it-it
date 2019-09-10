---
title: Riepilogo dei tipi di traccia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856007"
---
# <a name="trace-type-summary"></a>Riepilogo dei tipi di traccia
I [livelli di origine](https://go.microsoft.com/fwlink/?LinkID=94943) definiscono diversi livelli di traccia: Critical, Error, Warning, Information e Verbose, oltre a fornire una descrizione del `ActivityTracing` flag, che attiva o disattiva l'output degli eventi relativi al limite della traccia e al trasferimento di attività.  
  
 È anche possibile esaminare [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) per i tipi di traccia che possono essere emessi da <xref:System.Diagnostics>.  
  
 Nella tabella seguente sono elencati quelli più importanti.  
  
|Tipo di traccia|DESCRIZIONE|  
|----------------|-----------------|  
|Critico|Errore irreversibile o arresto anomalo dell'applicazione.|  
|Errore|Errore risolvibile.|  
|Avviso|Messaggio informativo.|  
|Informazioni|Problema non critico.|  
|Dettagliato|Traccia di debug.|  
|Start|Avvio di un'unità logica di elaborazione.|  
|Sospendi|Sospensione di un'unità logica di elaborazione.|  
|Riprendi|Ripresa di un'unità logica di elaborazione.|  
|Arresto|Interruzione di un'unità logica di elaborazione.|  
|Trasferimento|Modifica dell'identità di correlazione.|  
  
 Un'attività è definita come una combinazione dei tipi di traccia riportati sopra.  
  
 Quella che segue è un'espressione regolare che definisce un'attività ideale in un ambito locale (origine di traccia),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Ciò significa che un'attività deve soddisfare le condizioni seguenti.  
  
- Deve avviarsi e arrestarsi rispettivamente con tracce Start e Stop.  
  
- Deve avere una traccia Transfer subito prima di una traccia Suspend o Resume  
  
- Non deve avere nessuna traccia tra le tracce Suspend e Resume, se esistono  
  
- Può avere un numero qualsiasi di tracce Critical/Error/Warning/Information/Verbose/Transfer, a condizione che vengano rispettate le condizioni precedenti  
  
 Quella che segue è un'espressione regolare che definisce un'attività ideale in ambito globale,  
  
`R+`  
  
 con R che è l'espressione regolare per un'attività nell'ambito locale. Ciò si traduce in,  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
