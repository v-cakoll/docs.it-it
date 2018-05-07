---
title: Errore di caricamento della DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="error-in-loading-dll-visual-basic"></a>Errore di caricamento della DLL (Visual Basic)
Una libreria di collegamento dinamico (DLL) è una libreria specificata nel `Lib` clausola di un `Declare` istruzione. Possibili cause di questo errore includono:  
  
-   Il file non è un eseguibile DLL.  
  
-   Il file non è una DLL di Microsoft Windows.  
  
-   La DLL fa riferimento a un'altra DLL che non è presente.  
  
-   La DLL o riferimento non è in una directory specificata nel percorso.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se il file è un file di testo di origine e pertanto non eseguibile DLL, deve essere compilato e collegato a un modulo eseguibile DLL.  
  
-   Se il file non è una DLL di Microsoft Windows, è possibile ottenere l'equivalente di Microsoft Windows.  
  
-   Se la DLL fa riferimento a un'altra DLL che non è presente, ottenere la DLL di cui viene fatto riferimento e renderli disponibili.  
  
-   Se la DLL o riferimento non è in una directory specificata dal percorso, spostare il file DLL in una directory a cui fa riferimento.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
