---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858429"
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
  
 Tipo di accesso: Sola lettura  
  
 Lunghezza massima consentita della matrice.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Byte massimi consentiti restituiti per ogni lettura.  
  
### <a name="maxdepth"></a>MaxDepth  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Profondità massima dei nodi annidati per ogni lettura.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Caratteri massimi consentiti in un nome di tabella.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Caratteri massimi consentiti nel contenuto di un elemento XML.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
