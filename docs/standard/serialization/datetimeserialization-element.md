---
title: <dateTimeSerialization> Elemento
description: Questo articolo descrive l' <dateTimeSerialization> elemento, che determina la modalità di serializzazione degli oggetti DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375817"
---
# <a name="datetimeserialization-element"></a>\<Elemento dateTimeSerialization>
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
  
|Attributi|Description|  
|----------------|-----------------|  
|`mode`|Facoltativa. Specifica la modalità di serializzazione. Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>. Il valore predefinito è **RoundTrip**.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|system.xml.serialization|L'elemento di primo livello per il controllo della serializzazione XML.|  
  
## <a name="remarks"></a>Osservazioni  
 Nelle versioni 1,0, 1,1, 2,0 e versioni successive del .NET Framework, quando questa proprietà è impostata su **local**, <xref:System.DateTime> gli oggetti vengono sempre formattati come ora locale. Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati. Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.  
  
 Nella versione 2,0 e nelle versioni successive del .NET Framework la cui proprietà è impostata su **round trip**, <xref:System.DateTime> gli oggetti vengono esaminati per determinare se si trovano in locale, UTC o in un fuso orario non specificato. Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate. Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Schema del file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md)
- [\<Elemento> schemaImporterExtensions](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [\<aggiungere> elemento per \< schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [\<System. XML. Serialization> elemento](../../../docs/standard/serialization/system-xml-serialization-element.md)
