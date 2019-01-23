---
title: Errore di caricamento della DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 76a0a443fd9f8a6dec5ead24bc75c97d89d6c36b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518462"
---
# <a name="error-in-loading-dll-visual-basic"></a>Errore di caricamento della DLL (Visual Basic)
Una libreria di collegamento dinamico (DLL) è una libreria specificata nel `Lib` clausola di un `Declare` istruzione. Possibili cause di questo errore includono:  
  
-   Il file non è un eseguibile DLL.  
  
-   Il file non è una DLL di Microsoft Windows.  
  
-   La DLL fa riferimento a un'altra DLL che non è presente.  
  
-   La DLL o cui si fa riferimento non è in una directory specificata nel percorso.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se il file è un file di testo di origine e pertanto non eseguibile DLL, deve essere compilato e collegato a un modulo DLL-file eseguibile.  
  
-   Se il file non è una DLL di Microsoft Windows, ottenere l'equivalente di Windows Microsoft.  
  
-   Se la DLL fa riferimento a un'altra DLL che non è presente, ottenere la DLL di cui viene fatto riferimento e renderlo disponibile.  
  
-   Se la DLL o cui si fa riferimento non è in una directory specificata dal percorso, spostare la DLL in una directory di cui viene fatto riferimento.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
