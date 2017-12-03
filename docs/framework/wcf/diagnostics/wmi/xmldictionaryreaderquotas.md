---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Sintassi  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe XmlDictionaryReaderQuotas non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe XmlDictionaryReaderQuotas presenta le proprietà seguenti:  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Lunghezza massima consentita della matrice.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Byte massimi consentiti restituiti per ogni lettura.  
  
### <a name="maxdepth"></a>MaxDepth  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Profondità massima dei nodi annidati per ogni lettura.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Caratteri massimi consentiti in un nome di tabella.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Caratteri massimi consentiti nel contenuto di un elemento XML.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
