---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956546"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe TcpTransportBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe TcpTransportBindingElement dispone delle proprietà seguenti:  
  
### <a name="connectionpoolsettings"></a>ConnectionPoolSettings  
 Tipo di dati: TcpConnectionPoolSettings  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni del pool di connessioni.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di richieste di connessioni in coda che possono essere in sospeso.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica se Teredo (una tecnologia per l'indirizzamento dei client dietro a firewall) è attivata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
