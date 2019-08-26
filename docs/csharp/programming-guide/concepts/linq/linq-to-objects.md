---
title: LINQ to Objects (C#)
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 9e20b2c7278787671c7a27646b7cbaac78b57d5f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591860"
---
# <a name="linq-to-objects-c"></a>LINQ to Objects (C#)
Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md). È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La raccolta può essere definita dall'utente o restituita da un'API di .NET Framework.  
  
 Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte. In passato, era necessario scrivere cicli `foreach` complessi che specificavano come recuperare i dati da una raccolta. Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.  
  
 Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `foreach` tradizionali:  
  
1. Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.  
  
2. Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.  
  
3. Possono essere trasferiti in altre origini dati con modifiche minime o nulle.  
  
 In generale, più è complessa l'operazione da eseguire sui dati, maggiore sarà il vantaggio che si potrà trarre dall'uso di LINQ rispetto alle tecniche di iterazione tradizionali.  
  
 Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati. Tali informazioni non devono essere ritenute esaustive.  
  
## <a name="in-this-section"></a>In questa sezione  
 [LINQ e stringhe (C#)](./linq-and-strings.md)  
 Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe. Include anche collegamenti ad argomenti che illustrano questi principi.  
  
 [LINQ e reflection (C#)](./linq-and-reflection.md)  
 Collegamenti a un esempio che illustra l'uso di reflection in LINQ.  
  
 [Directory di file e LINQ (C#)](./linq-and-file-directories.md)  
 Viene illustrato come usare LINQ per interagire con i file system. Include anche collegamenti ad argomenti che illustrano questi concetti.  
  
 [Procedura: Eseguire una query su un ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md)  
 Viene illustrato come eseguire una query su un oggetto ArrayList in C#.  
  
 [Procedura: Aggiungere metodi personalizzati per query LINQ (C#)](./how-to-add-custom-methods-for-linq-queries.md)  
 Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [Language-Integrated Query (LINQ) (C#)](./index.md)  
 Vengono specificati collegamenti ad argomenti che descrivono LINQ e offrono esempi di codice per l'esecuzione di query.
