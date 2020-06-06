---
title: Elemento <system.xml.serialization>
description: Questo articolo descrive l'elemento < System. XML. Serialization >, che è l'elemento di livello principale per il controllo della serializzazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289486"
---
# <a name="systemxmlserialization-element"></a>\<system.xml.serialization> Elemento

L'elemento di primo livello per il controllo della serializzazione XML. Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../framework/configure-apps/file-schema/index.md).

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a>Sintassi

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

No.

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<dateTimeSerialization>Elemento](datetimeserialization-element.md)|Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.|
|[\<schemaImporterExtensions>Elemento](schemaimporterextensions-element.md)|Contiene tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<configuration>Elemento](../../framework/configure-apps/file-schema/configuration-element.md)|Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.|

## <a name="example"></a>Esempio

Nell'esempio di codice riportato di seguito viene illustrato come specificare la modalità di serializzazione di un oggetto <xref:System.DateTime> e l'aggiunta dei tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a>Vedi anche

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Schema del file di configurazione](../../framework/configure-apps/file-schema/index.md)
- [\<dateTimeSerialization>Elemento](datetimeserialization-element.md)
- [\<schemaImporterExtensions>Elemento](schemaimporterextensions-element.md)
- [\<add>Elemento per\<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
