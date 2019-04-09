---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145678"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement
BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe BinaryMessageEncodingBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe BinaryMessageEncodingBindingElement dispone delle proprietà seguenti.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.  
  
## <a name="maxsessionsize"></a>MaxSessionSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Valore che specifica la dimensione, in byte, del buffer usato per la codifica.  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.  
  
## <a name="readerquotas"></a>ReaderQuotas  
 Tipo di dati: XmlDictionaryReaderQuotas  
  
 Tipo di accesso: Sola lettura  
  
 Quote dei lettori.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
