---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199474"
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
