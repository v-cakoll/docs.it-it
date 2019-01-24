---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: adf7d8958e2361d6e26576f6b20321b9c5666d1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688883"
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ReliableSessionBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ReliableSessionBindingElement ha le proprietà seguenti:  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo che una destinazione attende prima di inviare un acknowledgment all'origine del messaggio sui canali affidabili creati dalla factory.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica se è attivato il controllo di flusso.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Specifica il limite massimo di tempo per cui il canale consente all'altra parte della comunicazione di non inviare messaggi prima di generare un errore per il canale.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di canali che possono attendere nel listener prima di essere accettati.  
  
### <a name="maxretrycount"></a>MaxRetryCount  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di tentativi di ritrasmissione di un messaggio per cui un canale affidabile non ha ricevuto un acknowledgment, tramite una chiamata a `Send` sul canale sottostante.  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Dimensione massima della finestra di trasferimento per la sessione affidabile.  
  
### <a name="ordered"></a>Ordered  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica se è garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion  
 Tipo di dati: numero intero  
  
 Tipo di accesso: Sola lettura  
  
 Numero intero che specifica la versione del protocollo WS-ReliableMessaging usata nella sessione affidabile.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
