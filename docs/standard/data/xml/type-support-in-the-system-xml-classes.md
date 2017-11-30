---
title: Supporto di tipi di dati nelle classi System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a>Supporto di tipi di dati nelle classi System.Xml
In .NET Framework versione 2.0 le classi principali XML sono state migliorate per includere funzionalità di supporto dei tipi di dati. Le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> includono funzionalità di supporto dei tipi che comprendono la capacità di conversione tra tipi XML Schema e tipi CLR (Common Language Runtime).  
  
 In .NET Framework versione 2.0 le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> sono state migliorate per includere funzionalità di supporto dei tipi di dati.  
  
-   Il <xref:System.Xml.XmlReader> e <xref:System.Xml.XPath.XPathNavigator> ciascuna delle classi include un **SchemaInfo** proprietà che restituisce le informazioni sullo schema in un nodo.  
  
-   Il **ReadContentAs** e **ReadElementContentAs** e i metodi sulla <xref:System.Xml.XmlReader> classe leggere un valore di testo e convertirlo in un valore CLR con una singola chiamata al metodo.  
  
-   Il metodo <xref:System.Xml.XmlWriter.WriteValue%2A> nella classe <xref:System.Xml.XmlWriter> converte un tipo CLR in un tipo XML Schema durante la scrittura XML.  
  
-   Il **ValueAs** e <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> proprietà la <xref:System.Xml.XPath.XPathNavigator> classe restituisce un valore di nodo e convertirlo in un valore CLR con una singola chiamata al metodo.  
  
> [!NOTE]
>  In .NET Framework versione 1.0 era necessario convertire la classe <xref:System.Xml.XmlConvert> tra il tipo XML Schema e il tipo CLR.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Mapping dei tipi di dati XML ai tipi CLR](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 Vengono descritti i mapping predefiniti dei tipi di dati XML ai tipi di dati CLR.  
  
 [Note sull'implementazione di supporto tipo XML](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 Vengono illustrati alcuni dettagli relativi all'implementazione del supporto per i tipi di dati.  
  
 [Conversione di tipi di dati XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 Viene descritto come usare la classe <xref:System.Xml.XmlConvert> per eseguire la conversione tra tipi XML Schema e tipi CLR.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Accesso sicuro ai dati XML tipizzati con XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
