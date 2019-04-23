---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978172"
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe MtomMessageEncodingBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe MtomMessageEncodingBindingElement dispone delle proprietà seguenti:  
  
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

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
