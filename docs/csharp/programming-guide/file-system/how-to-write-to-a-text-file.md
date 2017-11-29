---
title: 'Procedura: scrivere in un file di testo (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Procedura: scrivere in un file di testo (Guida per programmatori C#)
In questi esempi vengono mostrati vari modi per scrivere testo in un file.  I primi due esempi usano metodi pratici statici nella classe <xref:System.IO.File?displayProperty=nameWithType> per scrivere ogni elemento di qualsiasi oggetto IEnumerable\<string> e una stringa in un file di testo.  Nell'esempio 3 viene illustrato come aggiungere testo a un file quando è necessario elaborare individualmente ogni riga mentre si scrive nel file.  Gli esempi da 1 a 3 sovrascrivono tutto il contenuto esistente nel file, ma l'esempio 4 mostra come aggiungere il testo a un file esistente.  
  
 In tutti gli esempi vengono scritti valori letterali stringa nei file, ma può essere più opportuno utilizzare il metodo <xref:System.String.Format%2A>, che presenta molti controlli per la scrittura di tipi diversi di valori giustificati a destra o a sinistra in un campo, con o senza riempimento e così via.  È anche possibile usare la funzionalità di [interpolazione di stringhe](../../../csharp/language-reference/keywords/interpolated-strings.md) di C#.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 In tutti gli esempi vengono scritti valori letterali stringa nei file, ma può essere più opportuno utilizzare il metodo <xref:System.String.Format%2A>, che presenta molti controlli per la scrittura di tipi diversi di valori giustificati a destra o a sinistra in un campo, con o senza riempimento e così via.  È anche possibile usare la funzionalità di [interpolazione di stringhe](../../../csharp/language-reference/keywords/interpolated-strings.md) di C#.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il file esiste ed è di sola lettura.  
  
-   Il nome del percorso è troppo lungo.  
  
-   Il disco è pieno.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md)  
 [Come salvare una raccolta di oggetti personalizzati nella memoria locale](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
