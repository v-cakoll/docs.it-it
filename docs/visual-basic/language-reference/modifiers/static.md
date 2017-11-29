---
title: Static (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e08f46076281e766a5bc0b99cd61fee9cd41ece5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Specifica che uno o più variabili locali dichiarate devono continuare a esistere e conservano i valori più recenti dopo il termine della procedura in cui sono dichiarati.  
  
## <a name="remarks"></a>Note  
 In genere, una variabile locale in una routine cessa di esistere non appena la routine verrà interrotta. Una variabile statica continua a esistere e mantiene il valore più recente. La variabile non viene reinizializzata alla successiva che il codice chiama la routine, e contiene ancora il valore più recente che è assegnato. Una variabile statica continua a esistere per la durata della classe o modulo in cui è definita in.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile utilizzare `Static` solo su variabili locali. Ciò significa che il contesto della dichiarazione per un `Static` variabile deve essere una routine o un blocco in una stored procedure e non può trattarsi di un file di origine, lo spazio dei nomi, classe, struttura o modulo.  
  
     Non è possibile utilizzare `Static` all'interno di una routine di struttura.  
  
-   I tipi di dati di `Static` non è possibile dedurre le variabili locali. Per ulteriori informazioni, vedere [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Modificatori combinati.** Non è possibile specificare `Static` con `ReadOnly`, `Shadows`, o `Shared` nella stessa dichiarazione.  
  
## <a name="behavior"></a>Comportamento  
 Quando si dichiara una variabile statica in un `Shared` procedure, solo una copia della variabile statica è disponibile per l'intera applicazione. Si chiama un `Shared` nome procedura utilizzando la classe, non una variabile che punta a un'istanza della classe.  
  
 Quando si dichiara una variabile statica in una routine che non è `Shared`, solo una copia della variabile è disponibile per ogni istanza della classe. Si chiama una routine non condivisa tramite una variabile che punta a una specifica istanza della classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'uso di `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 Il `Static` variabile `totalSales` viene inizializzata su 0, solo una volta. Ogni volta che si immette `updateSales`, `totalSales` presenta ancora il valore più recente è calcolato.  
  
 Il `Static` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
