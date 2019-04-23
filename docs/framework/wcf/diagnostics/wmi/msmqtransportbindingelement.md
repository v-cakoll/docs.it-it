---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770750"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
 Tipo di accesso: Sola lettura  
  
 Dimensione massima del pool che contiene oggetti di messaggi MSMQ interni.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore di enumerazione che indica il trasporto per il canale delle comunicazioni in coda utilizzato da questa associazione.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Restituisce un valore booleano che indica se convertire gli indirizzi delle code mediante Active Directory.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
