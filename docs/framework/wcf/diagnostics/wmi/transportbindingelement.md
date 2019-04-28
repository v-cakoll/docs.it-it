---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641619"
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
