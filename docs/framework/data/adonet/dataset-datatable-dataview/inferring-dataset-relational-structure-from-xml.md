---
title: Deduzione della struttura relazionale di dataset da XML
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: 9b1932807058777a532457c99efc49f3ddfdf4ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204811"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Deduzione della struttura relazionale di dataset da XML
La struttura relazionale, o schema, di un tipo <xref:System.Data.DataSet> è costituita da tabelle, colonne, vincoli e relazioni. Quando si carica un tipo <xref:System.Data.DataSet> dall'XML, lo schema può essere predefinito oppure creato, implicitamente o tramite inferenza, dall'XML caricato. Per ulteriori informazioni sul caricamento dello schema e del contenuto di <xref:System.Data.DataSet> un da XML, vedere [caricamento di un DataSet da](loading-a-dataset-from-xml.md) XML e [caricamento delle informazioni sullo schema del set di dati da XML](loading-dataset-schema-information-from-xml.md).  
  
 Se lo schema di un <xref:System.Data.DataSet> oggetto viene creato da XML, il metodo preferito consiste nello specificare in modo esplicito lo schema utilizzando il linguaggio XSD (XML Schema Definition), come descritto in derivazione della [struttura relazionale del set di dati da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)o XML-Data Reduced (XDR). Se nell'XML non è disponibile un XML Schema o uno schema XDR, è possibile inferire lo schema del tipo <xref:System.Data.DataSet> dalla struttura degli elementi e degli attributi XML.  
  
 Contenuto della sezione vengono descritte le regole relative all'inferenza dello schema del tipo <xref:System.Data.DataSet> mediante l'illustrazione degli elementi e degli attributi XML, delle relative strutture e dello schema inferito del tipo <xref:System.Data.DataSet> risultante.  
  
 Non è necessario includere in un processo di inferenza tutti gli attributi presenti in un documento XML. È possibile che negli attributi qualificati dallo spazio dei nomi siano inclusi metadati importanti per il documento XML ma non per lo schema del tipo <xref:System.Data.DataSet>. Il metodo <xref:System.Data.DataSet.InferXmlSchema%2A> consente di specificare degli spazi dei nomi da ignorare durante il processo di inferenza. Per ulteriori informazioni, vedere [caricamento di informazioni sullo schema del set di dati da XML](loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Riepilogo del processo di inferenza dello schema DataSet](summary-of-the-dataset-schema-inference-process.md)  
 Viene fornito un riepilogo estremamente dettagliato delle regole per l'inferenza dello schema di un tipo <xref:System.Data.DataSet> dall'XML.  
  
 [Deduzione di tabelle](inferring-tables.md)  
 Vengono descritti gli elementi XML inferiti come tabelle in un tipo <xref:System.Data.DataSet>.  
  
 [Deduzione di colonne](inferring-columns.md)  
 Vengono descritti gli elementi e gli attributi XML inferiti come colonne di tabelle.  
  
 [Deduzione di relazioni](inferring-relationships.md)  
 Vengono descritti gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> creati per le tabelle annidate inferite.  
  
 [Deduzione del testo dell'elemento](inferring-element-text.md)  
 Vengono descritte le colonne create per il testo negli elementi XML e vengono illustrati i casi in cui tale testo viene ignorato.  
  
 [Limitazioni all'inferenza](inference-limitations.md)  
 Vengono illustrate le limitazioni dell'inferenza dello schema.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](using-xml-in-a-dataset.md)  
 Viene descritta l'interazione dell'oggetto <xref:System.Data.DataSet> con i dati XML.  
  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un tipo <xref:System.Data.DataSet> creato da uno schema XSD (XML Schema Definition Language).  
  
 [Panoramica di ADO.NET](../ado-net-overview.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET, nonché il relativo uso per accedere alle origini dati esistenti e per gestire i dati dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
