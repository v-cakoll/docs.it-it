---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 5ec2ae0db7239ff0c376ab4a8f050cc4f1df4f71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683972"
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ConnectionOrientedTransportBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ConnectionOrientedTransportBindingElement dispone delle proprietà seguenti:  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 TimeSpan che specifica l'intervallo di tempo per il completamento dell'inizializzazione del canale prima del timeout.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Dimensione del buffer usata per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.  
  
### <a name="hostnamecomparisonmode"></a>HostnameComparisonMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se viene usato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Dimensione massima del buffer da usare.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di thread asincroni in sospeso disponibili per l'elaborazione delle connessioni in ingresso del servizio.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di connessioni in sospeso.  
  
### <a name="transfermode"></a>TransferMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore che specifica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
