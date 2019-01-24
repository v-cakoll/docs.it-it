---
title: La codifica non può essere impostata su Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 99dbd1a068cabca7f57b6d5e8dd13e1069aede65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691329"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>La codifica non può essere impostata su Nothing
Un tentativo di leggere o scrivere in un file non è riuscito perché il parametro `encoding` è stato impostato su `Nothing` ma richiede un valore valido.  
  
 <xref:System.Text.Encoding> consente di determinare quale codifica usare durante la scrittura in un file. Il valore predefinito è UTF-8.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Specificare un valore valido per il parametro `encoding` .  
  
## <a name="see-also"></a>Vedere anche
- [Codifiche dei file](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [Lettura da file](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Scrittura su file](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
