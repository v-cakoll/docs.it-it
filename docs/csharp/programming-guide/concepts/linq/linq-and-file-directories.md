---
title: Directory di file e LINQ (C#)
description: Queste risorse LINQ C# per le operazioni di file system non vengono usate per modificare il contenuto dei file o delle cartelle.
ms.date: 07/20/2015
ms.assetid: b66c55e4-0f72-44e5-b086-519f9962335c
ms.openlocfilehash: ac00e29f90ee1c04ab9978b6ada3ae5f28991a1c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165661"
---
# <a name="linq-and-file-directories-c"></a>Directory di file e LINQ (C#)

Molte file system operazioni sono essenzialmente query e sono pertanto ideali per l'approccio LINQ.  
  
 Le query in questa sezione non sono distruttive. Non vengono usate per modificare il contenuto dei file o delle cartelle originali. Ne consegue la regola per cui le query non dovrebbero causare effetti collaterali. In generale, il codice (incluse le query che eseguono operatori create/update/delete) che modifica i dati di origine deve essere mantenuto separato dal codice che esegue esclusivamente query sui dati.  
  
 Questa sezione contiene i seguenti argomenti:  
  
 [Come eseguire una query per i file con un attributo o un nome specifico (C#)](./how-to-query-for-files-with-a-specified-attribute-or-name.md)\
 La procedura illustra come cercare file esaminando una o più proprietà del relativo oggetto <xref:System.IO.FileInfo>.  
  
 [Come raggruppare i file per estensione (LINQ) (C#)](./how-to-group-files-by-extension-linq.md)\
 La procedura illustra come restituire gruppi dell'oggetto <xref:System.IO.FileInfo> in base all'estensione del file.  
  
 [Come eseguire una query per il numero totale di byte in un set di cartelle (LINQ) (C#)](./how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)\
 La procedura illustra come restituire il numero totale di byte in tutti i file all'interno di un albero di directory specificato.  
  
 [Come confrontare il contenuto di due cartelle (LINQ) (C#)](./how-to-compare-the-contents-of-two-folders-linq.md)s  
 La procedura illustra come restituire tutti i file presenti in due cartelle specifiche e tutti i file presenti in una cartella, ma non nell'altra.  
  
 [Come eseguire una query per il file o i file più grandi in un albero di directory (LINQ) (C#)](./how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)\
 La procedura illustra come ripristinare il file più grande, il file più piccolo o un numero specificato di file in un albero di directory.  
  
 [Come eseguire una query per i file duplicati in un albero di directory (LINQ) (C#)](./how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)\
 La procedura illustra come raggruppare tutti i nomi file che si verificano in più di una posizione all'interno di un albero di directory specificato. Viene anche illustrato come eseguire confronti più complessi basati su un operatore di confronto personalizzato.  
  
 [Come eseguire una query sul contenuto dei file in una cartella (LINQ) (C#)](./how-to-query-the-contents-of-files-in-a-folder-lin.md)\
 La procedura illustra come eseguire l'iterazione nelle cartelle in un albero, aprire ogni file ed eseguire query sul contenuto del file.  
  
## <a name="comments"></a>Commenti  
 La creazione di un'origine dati che rappresenta accuratamente il contenuto del file system e gestisce correttamente le eccezioni comporta un certo livello di complessità. Negli esempi riportati in questa sezione viene creata una raccolta di snapshot di oggetti <xref:System.IO.FileInfo>, che rappresenta tutti i file in una cartella radice specificata e in tutte le relative sottocartelle. Lo stato effettivo di ogni <xref:System.IO.FileInfo> può cambiare nel tempo tra l'inizio e la fine dell'esecuzione di una query. Ad esempio, è possibile creare un elenco di oggetti <xref:System.IO.FileInfo> da usare come origine dati. Se si tenta di accedere alla proprietà `Length` in una query, l'oggetto <xref:System.IO.FileInfo> tenterà di accedere al file system per aggiornare il valore di `Length`. Se il file non esiste più, nella query si otterrà un'eccezione <xref:System.IO.FileNotFoundException>, anche se non si sta eseguendo una query direttamente nel file system. Alcune query in questa sezione usano un metodo separato che impiega queste particolari eccezioni in determinati casi. Un'altra opzione consiste nel mantenere l'origine dati aggiornata in modo dinamico tramite <xref:System.IO.FileSystemWatcher>.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Objects (C#)](./linq-to-objects.md)
