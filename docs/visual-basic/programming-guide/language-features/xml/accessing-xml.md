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
ms.openlocfilehash: 282b7d91ec7cfe2f587c67bc9a982f0da22ad925
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410309"
---
# <a name="accessing-xml-in-visual-basic"></a>Accesso a XML in Visual Basic
Visual Basic fornisce proprietà Axis XML per l'accesso e l'esplorazione delle [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] strutture. Queste proprietà utilizzano una sintassi speciale per consentire l'accesso agli elementi e agli attributi specificando i nomi XML.  
  
 Nella tabella seguente sono elencate le funzionalità del linguaggio che consentono di accedere agli elementi e agli attributi XML in Visual Basic.  
  
### <a name="xml-axis-properties"></a>Proprietà Axis XML  
  
|Descrizione proprietà|Esempio|Descrizione|  
|--------------------------|-------------|-----------------|  
|*child - asse*|`contact.<phone>`|Ottiene tutti `phone` gli elementi che sono elementi figlio dell' `contact` elemento.|  
|*attributo, asse*|`phone.@type`|Ottiene tutti `type` gli attributi dell' `phone` elemento.|  
|*descendant - asse*|`contacts...<name>`|Ottiene tutti `name` gli elementi dell' `contacts` elemento, indipendentemente dalla profondità della gerarchia in cui si verificano.|  
|*indicizzatore di estensione*|`contacts...<name>(0)`|Ottiene il primo `name` elemento dalla sequenza.|  
|*value*|`contacts...<name>.Value`|Ottiene la rappresentazione di stringa del primo oggetto nella sequenza o `Nothing` se la sequenza è vuota.|  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Accedere agli elementi discendenti XML](how-to-access-xml-descendant-elements.md)  
 Viene illustrato come utilizzare una proprietà asse discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML specificato.  
  
 [Procedura: Accedere agli elementi figlio XML](how-to-access-xml-child-elements.md)  
 Viene illustrato come utilizzare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.  
  
 [Procedura: accedere agli attributi XML](how-to-access-xml-attributes.md)  
 Viene illustrato come utilizzare una proprietà axis dell'attributo per accedere a tutti gli attributi XML con un nome specificato in un elemento XML.  
  
 [Procedura: Dichiarare e usare prefissi dello spazio dei nomi XML](how-to-declare-and-use-xml-namespace-prefixes.md)  
 Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e utilizzarlo per creare e accedere a elementi XML.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Proprietà Axis XML](../../../language-reference/xml-axis/index.md)  
 Vengono forniti collegamenti a sezioni che descrivono le varie proprietà di accesso XML.  
  
 [Cenni preliminari su LINQ to XML in Visual Basic](overview-of-linq-to-xml.md)  
 Viene fornita un'introduzione all'utilizzo di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Creazione di XML in Visual Basic](creating-xml.md)  
 Viene fornita un'introduzione all'utilizzo di valori letterali XML in Visual Basic.  
  
 [Modifica di XML in Visual Basic](manipulating-xml.md)  
 Vengono forniti collegamenti alle sezioni relative al caricamento e alla modifica di XML in Visual Basic.  
  
 [XML](index.md)  
 Vengono forniti collegamenti a sezioni che descrivono come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.
