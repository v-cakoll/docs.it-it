---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: a0e2ac250da3837b41134d3a04a21579a2fe923a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569037"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe MsmqBindingElementBase non definisce alcun metodo.  
  
## <a name="properties"></a>Proprietà  
 La classe MsmqBindingElementBase ha le proprietà seguenti:  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 URI che contiene il percorso della coda dei messaggi non recapitabili per ogni applicazione, in cui vengono collocati i messaggi scaduti o che non possono essere trasferiti o recapitati.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore di enumerazione che indica il tipo di coda dei messaggi non recapitabili da utilizzare.  
  
### <a name="durable"></a>Durevole  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se i messaggi elaborati da questa associazione sono durevoli o volatili.  
  
### <a name="exactlyonce"></a>ExactlyOnce  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che indica se i messaggi elaborati da questa associazione vengono ricevuti una sola volta.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di cicli di ripetizione dei tentativi di recapito dei messaggi all'applicazione ricevente.  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni per la gestione dei messaggi non elaborabili.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di tentativi immediati su un messaggio letto dalla coda dell'applicazione.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica l'intervallo di tempo tra i cicli di ripetizione dei tentativi di recapitare un messaggio che è impossibile recapitare immediatamente.  
  
### <a name="timetolive"></a>TimeToLive  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica per quanto tempo i messaggi elaborati da questa associazione possono rimanere nella coda prima di scadere.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che indica se i messaggi elaborati da questa associazione devono essere tracciati.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che indica se le copie dei messaggi elaborati da questa associazione devono essere archiviate nella coda journal di origine.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
