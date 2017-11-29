---
title: "Non è accessibile &#39; Main &#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Non è accessibile &#39; Main &#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;
Applicazioni della riga di comando devono avere un `Sub Main` definito. `Main`deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.  
  
 Per ulteriori informazioni su `Main`, vedere [NIB: Visual Basic versione di Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).  
  
 **ID errore:** BC30737  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Definire un `Public Sub Main` procedure per il progetto. Dichiara la classe come `Shared` se e solo se viene definita in una classe.  
  
## <a name="see-also"></a>Vedere anche  
 [NIB: versione di Visual Basic di Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Struttura di un programma Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
