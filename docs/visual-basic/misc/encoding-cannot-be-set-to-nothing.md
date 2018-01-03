---
title: "La codifica non può essere impostata su Nothing"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42baef6e0634849004290dce3db32e47f103282d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a>La codifica non può essere impostata su Nothing
Un tentativo di leggere o scrivere in un file non è riuscito perché il parametro `encoding` è stato impostato su `Nothing` ma richiede un valore valido.  
  
 <xref:System.Text.Encoding> consente di determinare quale codifica usare durante la scrittura in un file. Il valore predefinito è UTF-8.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Specificare un valore valido per il parametro `encoding` .  
  
## <a name="see-also"></a>Vedere anche  
 [Codifiche dei file](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [Lettura da file](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Scrittura su file](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)  
 [WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
