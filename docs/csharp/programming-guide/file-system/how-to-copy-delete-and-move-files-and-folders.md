---
title: 'Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56383873674998fc0d6417a2abf4fa72e498f08f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)
Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> e <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> dello spazio dei nomi <xref:System.IO?displayProperty=nameWithType>. Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente. Se si vuole fornire una finestra di dialogo di stato standard, vedere [Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Usare <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> per fornire eventi che consentano di calcolare lo stato quando si opera su più file. Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows. Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](https://msdn.microsoft.com/library/kztecsys).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come copiare file e directory.  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come spostare file e directory.  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eliminare file e directory.  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO?displayProperty=nameWithType>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [File system e Registro di sistema (Guida per programmatori C#)](index.md)  
 [Procedura: Creare una finestra di dialogo dello stato di avanzamento per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [I/O di file e di flussi](https://msdn.microsoft.com/library/k3352a4t)  
 [Attività di I/O comuni](https://msdn.microsoft.com/library/ms404278)
