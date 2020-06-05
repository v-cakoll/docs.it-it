---
title: LINQ to Objects
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 1dca449f12c312fd395be56ebcb426c3a63b64d0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84369063"
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](linq-to-xml.md). È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La raccolta può essere definita dall'utente o restituita da un'API di .NET Framework.  
  
 Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte. In passato, era necessario scrivere cicli `For Each` complessi che specificavano come recuperare i dati da una raccolta. Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.  
  
 Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `For Each` tradizionali:  
  
1. Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.  
  
2. Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.  
  
3. Possono essere trasferiti in altre origini dati con modifiche minime o nulle.  
  
 In generale, più è complessa l'operazione da eseguire sui dati, maggiore sarà il vantaggio che si potrà trarre dall'uso di LINQ rispetto alle tecniche di iterazione tradizionali.  
  
 Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati. Tali informazioni non devono essere ritenute esaustive.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))  
 Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe. Include anche collegamenti ad argomenti che illustrano questi principi.  
  
 [LINQ e Reflection (Visual Basic)](linq-and-reflection.md)  
 Collegamenti a un esempio che illustra l'uso di reflection in LINQ.  
  
 [LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))  
 Viene illustrato come usare LINQ per interagire con i file system. Include anche collegamenti ad argomenti che illustrano questi concetti.  
  
 [Procedura: eseguire una query su un ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md)  
 Viene illustrato come eseguire una query su un oggetto ArrayList in C#.  
  
 [Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)](how-to-add-custom-methods-for-linq-queries.md)  
 Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [LINQ (Language-Integrated Query) (Visual Basic)](index.md)  
 Vengono specificati collegamenti ad argomenti che descrivono LINQ e offrono esempi di codice per l'esecuzione di query.
