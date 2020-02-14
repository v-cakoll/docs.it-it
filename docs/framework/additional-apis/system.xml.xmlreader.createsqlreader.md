---
title: Metodo XmlReader. CreateSqlReader (System. Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215454"
---
# <a name="xmlreadercreatesqlreader-method"></a>Metodo XmlReader.CreateSqlReader

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

## <a name="returns"></a>Valori di codice restituiti

<xref:System.Xml.XmlReader>  
Oggetto usato per leggere i dati XML nel flusso.

## <a name="remarks"></a>Osservazioni

> [!WARNING]
> Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Xml>

**Assembly:** System. XML. dll

**Versioni .NET Framework:** Disponibile a partire da 2,0.
