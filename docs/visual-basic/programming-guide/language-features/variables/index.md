---
title: Variabili in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 79cd5629d4de6279eb370c18db617a5ad532108d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="variables-in-visual-basic"></a>Variabili in Visual Basic
Spesso è necessario archiviare i valori quando si eseguono calcoli con Visual Basic. È possibile ad esempio che si vogliano calcolare valori diversi, confrontarli ed eseguire operazioni su di essi a seconda del risultato del confronto. Per poter confrontare i valori è necessario archiviarli.  
  
## <a name="usage"></a>Utilizzo  
 Visual Basic, esattamente come la maggior parte dei linguaggi di programmazione, utilizza le variabili per archiviare i valori. Ogni *variabile* ha un nome, ovvero la parola usata per fare riferimento al valore contenuto nella variabile. Ogni variabile ha anche un tipo di dati che determina il genere di dati che la variabile può archiviare. Una variabile può rappresentare una matrice se deve archiviare un insieme indicizzato di elementi di dati strettamente correlati.  
  
 L'inferenza del tipo di variabile locale consente di dichiarare le variabili senza specificare esplicitamente un tipo di dati. In questo caso, il compilatore deduce il tipo della variabile in base al tipo dell'espressione di inizializzazione. Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
## <a name="assigning-values"></a>Assegnazione di valori  
 Le istruzioni di assegnazione consentono di eseguire i calcoli e assegnare il risultato a una variabile, come illustra l'esempio seguente.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Il segno di uguale (`=`) in questo esempio è un operatore di assegnazione, non un operatore di uguaglianza. Il valore viene assegnato alla variabile `applesSold`.  
  
 Per altre informazioni, vedere [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Variabili e proprietà  
 Analogamente a una variabile, una *proprietà* rappresenta un valore al quale è possibile accedere. Le proprietà sono tuttavia più complesse delle variabili. Le proprietà usano blocchi di codice che controllano come impostare e recuperare il valore della proprietà. Per altre informazioni, vedere [Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Risoluzione dei problemi relativi alle variabili](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
