---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 188a766807cd779ac51df390b1332641584dbb06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662712"
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement
TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe TextMessageEncodingBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe TextMessageEncodingBindingElement dispone delle proprietà seguenti:  
  
### <a name="encoding"></a>Codifica  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo di dati: XmlDictionaryReaderQuotas  
  
 Tipo di accesso: Sola lettura  
  
 Quote dei lettori.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
