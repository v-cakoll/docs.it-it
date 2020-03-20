---
title: Riepilogo dei tipi di traccia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674831"
---
# <a name="trace-type-summary"></a>Riepilogo dei tipi di traccia
[Livelli di origine](xref:System.Diagnostics.SourceLevels) definisce vari livelli di traccia: critico, errore, avviso, informazioni `ActivityTracing` e dettagliato, nonché una descrizione del flag, che attiva/disattiva l'output degli eventi di limite di traccia e di trasferimento dell'attività.  
  
 È inoltre <xref:System.Diagnostics.TraceEventType> possibile esaminare i tipi di tracce <xref:System.Diagnostics>che possono essere emessi da .  
  
 Nella tabella seguente sono elencati quelli più importanti.  
  
|Tipo di traccia|Descrizione|  
|----------------|-----------------|  
|Critico|Errore irreversibile o arresto anomalo dell'applicazione.|  
|Errore|Errore risolvibile.|  
|Avviso|Messaggio informativo.|  
|Informazioni|Problema non critico.|  
|Dettagliato|Traccia di debug.|  
|Inizia|Avvio di un'unità logica di elaborazione.|  
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
