---
title: Accesso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351741"
---
# <a name="accessing-xml-in-visual-basic"></a>Accesso a XML in Visual Basic
Visual Basic fornisce proprietà Axis XML per l'accesso e l'esplorazione di strutture [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Queste proprietà utilizzano una sintassi speciale per consentire l'accesso agli elementi e agli attributi specificando i nomi XML.  
  
 Nella tabella seguente sono elencate le funzionalità del linguaggio che consentono di accedere agli elementi e agli attributi XML in Visual Basic.  
  
### <a name="xml-axis-properties"></a>Proprietà Axis XML  
  
|Descrizione proprietà|Esempio|Descrizione|  
|--------------------------|-------------|-----------------|  
|*asse figlio*|`contact.<phone>`|Ottiene tutti gli elementi `phone` che sono elementi figlio dell'elemento `contact`.|  
|*asse degli attributi*|`phone.@type`|Ottiene tutti gli attributi di `type` dell'elemento `phone`.|  
|*asse discendente*|`contacts...<name>`|Ottiene tutti gli elementi `name` dell'elemento `contacts`, indipendentemente dalla profondità della gerarchia.|  
|*indicizzatore di estensione*|`contacts...<name>(0)`|Ottiene il primo elemento `name` dalla sequenza.|  
|*valore*|`contacts...<name>.Value`|Ottiene la rappresentazione di stringa del primo oggetto nella sequenza oppure `Nothing` se la sequenza è vuota.|  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Accedere agli elementi discendenti XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Viene illustrato come utilizzare una proprietà asse discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML specificato.  
  
 [Procedura: Accedere agli elementi figlio XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Viene illustrato come utilizzare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.  
  
 [Procedura: Accedere agli attributi XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Viene illustrato come utilizzare una proprietà axis dell'attributo per accedere a tutti gli attributi XML con un nome specificato in un elemento XML.  
  
 [Procedura: Dichiarare e usare prefissi dello spazio dei nomi XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e utilizzarlo per creare e accedere a elementi XML.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Proprietà Axis XML](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Vengono forniti collegamenti a sezioni che descrivono le varie proprietà di accesso XML.  
  
 [Cenni preliminari su LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Viene fornita un'introduzione all'utilizzo di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Viene fornita un'introduzione all'utilizzo di valori letterali XML in Visual Basic.  
  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Vengono forniti collegamenti alle sezioni relative al caricamento e alla modifica di XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Vengono forniti collegamenti a sezioni che descrivono come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.
