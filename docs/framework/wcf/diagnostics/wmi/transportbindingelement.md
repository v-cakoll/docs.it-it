---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 062b45eb5d627903142ca1a5fd4db6df0855384b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Tipo di dati: sint64  
  
 Tipo di accesso: sola lettura  
  
 Dimensioni massime del pool di buffer dell'associazione.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Tipo di dati: sint64  
  
 Tipo di accesso: sola lettura  
  
 Dimensioni massime di un messaggio elaborato dall'associazione.  
  
### <a name="scheme"></a>Scheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Schema URI del trasporto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
