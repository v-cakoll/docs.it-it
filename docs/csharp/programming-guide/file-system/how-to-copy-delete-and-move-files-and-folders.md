---
title: Come copiare, eliminare e spostare file e cartelle- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712273"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Come copiare, eliminare e spostare file e cartelle (C# guida per programmatori)
Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> e <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> dello spazio dei nomi <xref:System.IO?displayProperty=nameWithType>. Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente. Se si desidera fornire una finestra di dialogo di stato standard, vedere [come fornire una finestra di dialogo di stato per le operazioni sui file](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Usare <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> per fornire eventi che consentano di calcolare lo stato quando si opera su più file. Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows. Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](../../../standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come copiare file e directory.  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come spostare file e directory.  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eliminare file e directory.  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [File system e Registro di sistema (Guida per programmatori C#)](index.md)
- [Come specificare una finestra di dialogo di stato per le operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [I/O di file e di flussi](../../../standard/io/index.md)
- [Attività di I/O comuni](../../../standard/io/common-i-o-tasks.md)
