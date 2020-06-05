---
title: La codifica non può essere impostata su Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 41565d1aa3b69f6ad92d4bbf2b2f2170014aef87
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394479"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>La codifica non può essere impostata su Nothing
Un tentativo di leggere o scrivere in un file non è riuscito perché il parametro `encoding` è stato impostato su `Nothing` ma richiede un valore valido.  
  
 <xref:System.Text.Encoding> consente di determinare quale codifica usare durante la scrittura in un file. Il valore predefinito è UTF-8.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Specificare un valore valido per il parametro `encoding` .  
  
## <a name="see-also"></a>Vedere anche

- [Codifiche dei file](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [Lettura da file](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Scrittura in file](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. computer. FileSystem. ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. computer. FileSystem. WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
