---
title: Metodo XmlReader. CreateSqlReader (System. Xml)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584134"
---
# <a name="xmlreadercreatesqlreader-method"></a>XmlReader. CreateSqlReader, metodo

Crea una nuova istanza di <xref:System.Xml.XmlReader> con il flusso, le impostazioni e le informazioni di contesto specificati per l'analisi.

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Parametri

- `input` <xref:System.IO.Stream>  
  Flusso che contiene i dati XML.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Impostazioni per la nuova istanza di <xref:System.Xml.XmlReader>. Il valore può essere `null`.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Informazioni sul contesto necessarie per analizzare il frammento XML. Il valore può essere `null`.

## <a name="returns"></a>Valore restituito

<xref:System.Xml.XmlReader>  
Oggetto usato per leggere i dati XML nel flusso.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Xml>

**Assembly:** System. XML. dll

**Versioni .NET Framework:** Disponibile a partire da 2,0.
