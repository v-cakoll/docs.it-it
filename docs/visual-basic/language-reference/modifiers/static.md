---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: de4f67fc5b60de48383a8ca886cff02b03830318
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814174"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Specifica che uno o più variabili locali dichiarate devono continuare a esistere e mantengono i valori più recenti dopo la terminazione della procedura in cui sono dichiarate.  
  
## <a name="remarks"></a>Note  
 In genere, una variabile locale in una procedura cessa di esistere, non appena la routine verrà interrotta. Una variabile statica continua a esistere e mantiene il valore più recente. La volta successiva che il codice chiama la procedura, la variabile non viene reinizializzata e contiene ancora il valore più recente che è assegnato a esso. Una variabile statica continua a esistere per la durata della classe o modulo in cui è definito.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile usare `Static` solo in variabili locali. Ciò significa che il contesto della dichiarazione per un `Static` variabile deve essere una routine o un blocco in una routine, e non può essere un file di origine, lo spazio dei nomi, classe, struttura o modulo.  
  
     Non è possibile usare `Static` all'interno di una routine di struttura.  
  
-   I tipi di dati di `Static` non è possibile dedurre le variabili locali. Per altre informazioni, vedere [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Modificatori combinati.** Non è possibile specificare `Static` assieme `ReadOnly`, `Shadows`, o `Shared` nella stessa dichiarazione.  
  
## <a name="behavior"></a>Comportamento  
 Quando si dichiara una variabile statica in un `Shared` procedure, solo una copia della variabile statica è disponibile per l'intera applicazione. Si chiama un `Shared` nome procedura utilizzando la classe, non una variabile che punta a un'istanza della classe.  
  
 Quando si dichiara una variabile statica in una routine che non sia `Shared`, solo una copia della variabile è disponibile per ogni istanza della classe. Si chiama una routine non condivise usando una variabile che punta a una specifica istanza della classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'uso di `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 Il `Static` variabile `totalSales` viene inizializzata su 0 solo una volta. Ogni volta che si immette `updateSales`, `totalSales` ha ancora il valore più recente che viene calcolata per tale.  
  
 Il `Static` modificatore può essere usato in questo contesto:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
