---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 643ab0f30c771f79df8ef7dd885013d5186fba59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe MsmqTransportBindingElement non definisce alcun metodo.  
  
## <a name="properties"></a>Proprietà  
 La classe MsmqTransportBindingElement ha le proprietà seguenti:  
  
### <a name="maxpoolsize"></a>MaxPoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Dimensione massima del pool che contiene oggetti di messaggi MSMQ interni.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Valore di enumerazione che indica il trasporto per il canale delle comunicazioni in coda utilizzato da questa associazione.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Restituisce un valore booleano che indica se convertire gli indirizzi delle code mediante Active Directory.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
