---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 0d5dc5c9b9bf2313d18c9fadb1a2adb87c1b11b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610786"
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
