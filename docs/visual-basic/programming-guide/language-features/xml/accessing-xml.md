---
title: Accesso a XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756962"
---
# <a name="accessing-xml-in-visual-basic"></a>Accesso a XML in Visual Basic
Visual Basic fornisce le proprietà axis XML per l'accesso e la navigazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] strutture. Queste proprietà utilizzano una sintassi speciale per poter accedere agli elementi e attributi specificando i nomi XML.  
  
 La tabella seguente elenca le funzionalità del linguaggio che consentono di accedere agli elementi XML e attributi in Visual Basic.  
  
### <a name="xml-axis-properties"></a>Proprietà Axis XML  
  
|Descrizione della proprietà|Esempio|Descrizione|  
|--------------------------|-------------|-----------------|  
|*asse child*|`contact.<phone>`|Ottiene tutti i `phone` gli elementi che sono elementi figlio del `contact` elemento.|  
|*asse attribute*|`phone.@type`|Ottiene tutti i `type` attributi del `phone` elemento.|  
|*asse descendant*|`contacts...<name>`|Ottiene tutti i `name` elementi del `contacts` elemento, indipendentemente dal livello di profondità della gerarchia che si verifichino.|  
|*extension indexer*|`contacts...<name>(0)`|Ottiene il primo `name` elemento dalla sequenza.|  
|*value*|`contacts...<name>.Value`|Ottiene la rappresentazione di stringa del primo oggetto nella sequenza, o `Nothing` se la sequenza è vuota.|  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Elementi discendenti XML di accesso](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Viene illustrato come usare una proprietà axis discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML specificato.  
  
 [Procedura: Accedere agli elementi figlio XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Viene illustrato come utilizzare un elemento figlio di proprietà dell'asse per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.  
  
 [Procedura: Attributi XML di accesso](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Viene illustrato come usare una proprietà axis dell'attributo per accedere a tutti gli attributi XML che hanno un nome specificato in un elemento XML.  
  
 [Procedura: Dichiarare e usare prefissi XML Namespace](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e usarlo per creare e accedere agli elementi XML.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Proprietà Axis XML](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Vengono forniti collegamenti alle sezioni che descrivono le varie proprietà di accesso XML.  
  
 [Cenni preliminari su LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Fornisce un'introduzione all'uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Fornisce un'introduzione all'uso di valori letterali XML in Visual Basic.  
  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Vengono forniti collegamenti alle sezioni sul caricamento e modifica di XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Vengono forniti collegamenti alle sezioni che descrivono come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.
