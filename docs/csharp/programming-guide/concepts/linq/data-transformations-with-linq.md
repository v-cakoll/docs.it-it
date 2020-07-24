---
title: Trasformazioni dati con LINQ (C#)
description: Informazioni su come usare le query LINQ in C# per trasformare i dati. È possibile modificare la sequenza ordinando e raggruppando e creando nuovi tipi utilizzando la clausola SELECT.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 6844cf2aa589f7516a9e40bc604c5f907ec6d311
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104025"
---
# <a name="data-transformations-with-linq-c"></a>Trasformazioni dati con LINQ (C#)
LINQ (Language-Integrated Query) non riguarda solo il recupero dei dati. È anche un potente strumento per la trasformazione dei dati. Utilizzando una query LINQ, è possibile utilizzare una sequenza di origine come input e modificarla in molti modi per creare una nuova sequenza di output. È possibile modificare la sequenza senza modificare gli elementi con operazioni di ordinamento e raggruppamento. Ma probabilmente la funzionalità più potente delle query LINQ è la possibilità di creare nuovi tipi. Questa operazione viene eseguita nella clausola [select](../../../language-reference/keywords/select-clause.md). Ad esempio, è possibile effettuare le attività seguenti:  
  
- Unire più sequenze di input in un'unica sequenza di output con un nuovo tipo.  
  
- Creare sequenze di output i cui elementi sono costituiti da una o più proprietà di ogni elemento nella sequenza di origine.  
  
- Creare sequenze di output i cui elementi sono costituiti dai risultati delle operazioni eseguite sui dati di origine.  
  
- Creare sequenze di output in un formato diverso. Ad esempio, è possibile trasformare i dati da righe SQL o file di testo in XML.  
  
 Questi sono solo alcuni esempi. Naturalmente, queste trasformazioni possono essere combinate in modi diversi nella stessa query. Inoltre, la sequenza di output di una query può essere usata come sequenza di input per una nuova query.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Unione di più input in un'unica sequenza di output  
 È possibile usare una query LINQ per creare una sequenza di output che contiene elementi da più di una sequenza di input. Nell'esempio seguente viene illustrato come combinare due strutture di dati in memoria, ma è possibile applicare gli stessi principi per combinare dati da origini XML, SQL o DataSet. Si supponga di avere questi tipi di classi:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 Nell'esempio riportato di seguito è visualizzata la query:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Per altre informazioni, vedere [Clausola join](../../../language-reference/keywords/join-clause.md) e [Clausola select](../../../language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Selezione di un sottoinsieme di ogni elemento di origine  
 Esistono due modi principali per selezionare un sottoinsieme di ogni elemento nella sequenza di origine:  
  
1. Per selezionare solo un membro dell'elemento di origine, usare l'operazione con punto. Nell'esempio seguente si supponga che un oggetto `Customer` contenga diverse proprietà pubbliche tra cui una stringa denominata `City`. Quando viene eseguita, questa query produce una sequenza di output di stringhe.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Per creare gli elementi che contengono più di una proprietà dall'elemento di origine, è possibile usare un inizializzatore di oggetto con un oggetto denominato o un tipo anonimo. Nell'esempio seguente viene illustrato l'uso di un tipo anonimo per incapsulare due proprietà da ogni elemento `Customer`:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Per altre informazioni, vedere [Inizializzatori di oggetto e di insieme](../../classes-and-structs/object-and-collection-initializers.md) e [Tipi anonimi](../../classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Trasformazione di oggetti in memoria in XML  
 Le query LINQ semplificano la trasformazione dei dati tra le strutture di dati in memoria, i database SQL, i set di dati ADO.NET e i documenti o i flussi XML. Nell'esempio seguente gli oggetti di una struttura di dati in memoria vengono trasformati in elementi XML.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Il codice genera il seguente output XML:  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Per altre informazioni, vedere [Creazione di alberi XML in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).  
  
## <a name="performing-operations-on-source-elements"></a>Esecuzione di operazioni su elementi di origine  
 Una sequenza di output potrebbe non contenere elementi o proprietà degli elementi della sequenza di origine. L'output potrebbe invece essere una sequenza di valori che viene calcolata usando gli elementi di origine come argomenti di input.

 Con la query seguente viene eseguita una sequenza di numeri che rappresentano raggi di cerchi, viene calcolata l'area per ogni raggio e viene restituita una sequenza di output contenente stringhe formattate con l'area calcolata.

 Ogni stringa per la sequenza di output verrà formattata utilizzando l' [interpolazione di stringhe](../../../language-reference/tokens/interpolated.md). Una stringa interpolata avrà un oggetto `$` davanti alle virgolette di apertura della stringa e le operazioni possono essere eseguite all'interno di parentesi graffe posizionate all'interno della stringa interpolata. Una volta eseguite queste operazioni, i risultati saranno concatenati.
  
> [!NOTE]
> La chiamata ai metodi nelle espressioni di query non è supportata se la query verrà traslata in un altro dominio. Ad esempio, non è possibile chiamare un normale metodo C# in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] perché SQL Server non offre alcun contesto. Tuttavia, è possibile eseguire il mapping delle stored procedure ai metodi e chiamarli. Per altre informazioni, vedere [Stored procedure](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (C#)](./index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](./linq-to-xml-overview.md)
- [Espressioni di query LINQ](../../../linq/index.md)
- [clausola SELECT](../../../language-reference/keywords/select-clause.md)
