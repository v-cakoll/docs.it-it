---
title: Come scrivere in un file di testo - Guida per programmatori C
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712247"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Come scrivere in un file di testo (Guida per programmatori C
In questi esempi vengono mostrati vari modi per scrivere testo in un file. I primi due esempi usano metodi pratici statici nella classe <xref:System.IO.File?displayProperty=nameWithType> per scrivere ogni elemento di qualsiasi oggetto `IEnumerable<string>` e una stringa in un file di testo. Nell'esempio 3 viene illustrato come aggiungere testo a un file quando è necessario elaborare individualmente ogni riga mentre si scrive nel file. Gli esempi da 1 a 3 sovrascrivono tutto il contenuto esistente nel file, ma l'esempio 4 mostra come aggiungere il testo a un file esistente.  
  
 Tutti gli esempi scrivono valori letterali stringa nei file. Per formattare il testo scritto in un file, usare il metodo <xref:System.String.Format%2A> o la funzionalità di [interpolazione di stringhe](../../language-reference/tokens/interpolated.md) di C#.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il file esiste ed è di sola lettura.  
  
- Il nome del percorso è troppo lungo.  
  
- Il disco è pieno.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](./index.md)
- [Come salvare una raccolta di oggetti personalizzati nella memoria locale](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
