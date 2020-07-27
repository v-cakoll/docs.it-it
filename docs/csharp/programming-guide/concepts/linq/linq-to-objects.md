---
title: LINQ to Objects (C#)
description: Informazioni sulle LINQ to Objects in C#, che usa query LINQ con qualsiasi raccolta IEnumerable o IEnumerable <T> senza un'API o un provider LINQ intermedio.
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 7b67690ee13f207441bc94155acd91047b63b3df
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165548"
---
# <a name="linq-to-objects-c"></a>LINQ to Objects (C#)

Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md). È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La raccolta può essere definita dall'utente o può essere restituita da un'API .NET.  
  
 Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte. In passato, era necessario scrivere cicli `foreach` complessi che specificavano come recuperare i dati da una raccolta. Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.  
  
 Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `foreach` tradizionali:  
  
- Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.  
  
- Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.  
  
- Possono essere trasferiti in altre origini dati con modifiche minime o nulle.  
  
 In generale, più è complessa l'operazione che si vuole eseguire sui dati, maggiore sarà il vantaggio che si realizzerà usando LINQ anziché le tecniche di iterazione tradizionali.  
  
 Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati. Non è destinato a essere esaustivo.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [LINQ e stringhe (C#)](./linq-and-strings.md)  
 Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe. Include anche collegamenti ad articoli che illustrano questi principi.  
  
 [LINQ e reflection (C#)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 Collegamenti a un esempio che illustra l'uso di reflection in LINQ.  
  
 [Directory di file e LINQ (C#)](./linq-and-file-directories.md)  
 Viene illustrato come usare LINQ per interagire con i file system. Sono inoltre inclusi collegamenti ad articoli in cui vengono illustrati questi concetti.  
  
 [Come eseguire una query su un ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md)  
 Viene illustrato come eseguire una query su un oggetto ArrayList in C#.  
  
 [Come aggiungere metodi personalizzati per le query LINQ (C#)](./how-to-add-custom-methods-for-linq-queries.md)  
 Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [LINQ (Language-Integrated Query) (C#)](./index.md)  
 Vengono forniti collegamenti ad articoli che illustrano LINQ e forniscono esempi di codice che eseguono query.
