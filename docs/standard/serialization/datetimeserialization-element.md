---
title: <dateTimeSerialization> Elemento
description: Questo articolo descrive l' <dateTimeSerialization> elemento, che determina la modalità di serializzazione degli oggetti DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289642"
---
# <a name="datetimeserialization-element"></a>\<dateTimeSerialization> Elemento
Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributi|Descrizione|  
|----------------|-----------------|  
|`mode`|Facoltativa. Specifica la modalità di serializzazione. Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>. Il valore predefinito è **RoundTrip**.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|system.xml.serialization|L'elemento di primo livello per il controllo della serializzazione XML.|  
  
## <a name="remarks"></a>Commenti  
 Nelle versioni 1,0, 1,1, 2,0 e versioni successive del .NET Framework, quando questa proprietà è impostata su **local**, <xref:System.DateTime> gli oggetti vengono sempre formattati come ora locale. Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati. Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.  
  
 Nella versione 2,0 e nelle versioni successive del .NET Framework la cui proprietà è impostata su **round trip**, <xref:System.DateTime> gli oggetti vengono esaminati per determinare se si trovano in locale, UTC o in un fuso orario non specificato. Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate. Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Schema del file di configurazione](../../framework/configure-apps/file-schema/index.md)
- [\<schemaImporterExtensions>Elemento](schemaimporterextensions-element.md)
- [\<add>Elemento per\<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
- [\<system.xml.serialization>Elemento](system-xml-serialization-element.md)
