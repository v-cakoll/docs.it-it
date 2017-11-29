---
title: Variabile &#39; &lt;variablename&gt;&#39; nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Variabile &#39; &lt;variablename&gt;&#39; nasconde una variabile in un blocco di inclusione
Una variabile è incluso in un blocco ha lo stesso nome di un'altra variabile locale.  
  
 **ID errore:** BC30616  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rinominare la variabile nel blocco in modo che non sia lo stesso come qualsiasi altra variabile locale. Ad esempio:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Una causa comune di questo errore è l'utilizzo di `Catch e As Exception` all'interno di un gestore eventi. In questo caso, assegnare un nome di `Catch` variabile del blocco `ex` anziché `e`.  
  
-   Un'altra causa comune di questo errore viene eseguito un tentativo di accedere a una variabile locale dichiarata all'interno di un `Try` blocco in un apposito `Catch` blocco. Per risolvere il problema, dichiarare la variabile all'esterno di `Try...Catch...Finally` struttura.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
