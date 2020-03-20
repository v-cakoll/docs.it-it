---
title: Metodo XmlReader.CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155739"
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
> Il `XmlReader.CreateSqlReader` metodo è interno e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta in nessun caso l'utilizzo di questo metodo in un'applicazione di produzione.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:**<xref:System.Xml>

**Assemblaggio:** System.xml.dll

Versioni di **.NET Framework:** Disponibile dalla 2.0.
