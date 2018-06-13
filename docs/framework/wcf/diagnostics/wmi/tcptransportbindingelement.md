---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485805"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Impostazioni del pool di connessioni.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di richieste di connessioni in coda che possono essere in sospeso.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se Teredo (una tecnologia per l'indirizzamento dei client dietro a firewall) è attivata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
