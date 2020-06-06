---
title: Strumento XML Schema Definition e serializzazione XML
description: Lo strumento XML Schema Definition genera file di classe C# o Visual Basic per uno schema XSD e genera una XML Schema da una libreria o da un file eseguibile.
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: c88770403d4c2abfb5ce99f44ea1bec1f8337545
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84279776"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Strumento XML Schema Definition e serializzazione XML

Lo strumento XML Schema Definition ([xsd. exe)](xml-schema-definition-tool-xsd-exe.md)viene installato insieme agli strumenti .NET Framework come parte del &reg; Software Development Kit (SDK) di Windows. Lo strumento è progettato principalmente per due scopi:  
  
- Per generare file di classe C# o Visual Basic conformi a uno schema XML Schema Definition Language (XSD) specifico. Lo strumento prende uno schema XML come argomento e restituisce un file contenente un numero di classi che, se serializzate con <xref:System.Xml.Serialization.XmlSerializer>, risultano conformi allo schema. Per informazioni su come usare lo strumento per generare classi conformi a uno schema specifico, vedere [Procedura: Usare lo strumento XML Schema Definition per generare classi e documenti XML Schema](xml-schema-def-tool-gen.md).  
  
- Per generare un documento XML Schema da un file con estensione dll o exe. Per visualizzare lo schema di un set di file creati o di uno schema modificato con attributi, passare il file DLL o EXE come argomento allo strumento per generare l'XML Schema. Per informazioni su come usare lo strumento per generare un documento XML Schema da un set di classi, vedere [Procedura: Usare lo strumento XML Schema Definition per generare classi e documenti XML Schema](xml-schema-def-tool-gen.md).  
  
Per ulteriori informazioni sull'utilizzo dello strumento, vedere [strumento XML Schema Definition (XSD. exe)](xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Data.DataSet>
- [Introduzione alla serializzazione XML](introducing-xml-serialization.md)
- [Strumento XML Schema Definition (XSD. exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
- [Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.](xml-schema-def-tool-gen.md)
- [Supporto dell'associazione all'XML Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
