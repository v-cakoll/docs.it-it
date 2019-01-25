---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668453"
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe TransportBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe TransportBindingElement dispone delle proprietà seguenti:  
  
### <a name="manualaddressing"></a>ManualAddressing  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Tipo di dati: sint64  
  
 Tipo di accesso: Sola lettura  
  
 Dimensioni massime del pool di buffer dell'associazione.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Tipo di dati: sint64  
  
 Tipo di accesso: Sola lettura  
  
 Dimensioni massime di un messaggio elaborato dall'associazione.  
  
### <a name="scheme"></a>Scheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Schema URI del trasporto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.TransportBindingElement>
