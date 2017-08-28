---
title: 'Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Procedura: copiare, eliminare e spostare file e cartelle (Guida per programmatori C#)
Gli esempi seguenti mostrano come copiare, spostare ed eliminare file e cartelle in modo sincrono usando le classi <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> e <xref:System.IO.DirectoryInfo?displayProperty=fullName> dello spazio dei nomi <xref:System.IO?displayProperty=fullName>. Questi esempi non forniscono un indicatore di stato o altri elementi di interfaccia utente. Se si vuole fornire una finestra di dialogo di stato standard, vedere [Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Usare <xref:System.IO.FileSystemWatcher?displayProperty=fullName> per fornire eventi che consentano di calcolare lo stato quando si opera su più file. Un altro approccio consiste nell'usare pInvoke per chiamare i metodi correlati ai file pertinenti nella shell di Windows. Per informazioni su come eseguire queste operazioni sui file in modo asincrono, vedere [I/O di file asincrono](https://msdn.microsoft.com/library/kztecsys).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come copiare file e directory.  
  
 [!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come spostare file e directory.  
  
 [!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eliminare file e directory.  
  
 [!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO?displayProperty=fullName>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [File system e Registro di sistema (Guida per programmatori C#)](index.md)   
 [Procedura: Fornire una finestra di dialogo dello stato per operazioni su file](how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [I/O di file e di flussi](https://msdn.microsoft.com/library/k3352a4t)   
 [Attività di I/O comuni](https://msdn.microsoft.com/library/ms404278)

