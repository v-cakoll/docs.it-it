---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c5fd2858688634ee48a67b930755fc3ceebbebf8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo di dati: XmlDictionaryReaderQuotas  
  
 Tipo di accesso: sola lettura  
  
 Quote dei lettori.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
