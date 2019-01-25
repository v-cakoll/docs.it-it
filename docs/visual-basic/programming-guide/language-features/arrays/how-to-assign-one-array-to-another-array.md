---
title: "Procedura: Assegnare una matrice a un'altra matrice (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: f2617d270caf5ed4ade68934486fee6afb6c413f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572721"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Procedura: Assegnare una matrice a un'altra matrice (Visual Basic)
Poiché le matrici sono gli oggetti, è possibile usarli nelle istruzioni di assegnazione, come altri tipi di oggetto. Una variabile di matrice contiene un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di classificazione e la lunghezza e un'assegnazione di copia solo questo puntatore.  
  
### <a name="to-assign-one-array-to-another-array"></a>Per assegnare una matrice a un'altra matrice  
  
1.  Assicurarsi che le due matrici hanno la stessa classificazione (numero di dimensioni) e tipi di dati compatibile.  
  
2.  Utilizzare un'istruzione di assegnazione standard per assegnare l'array di origine nella matrice di destinazione. Non seguire i nomi delle matrici tra parentesi.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 Quando si assegna una matrice a un altro, si applicano le regole seguenti:  
  
-   **Numeri di dimensioni uguali.** La classificazione (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.  
  
     Le classificazioni delle due matrici sono uguali, le dimensioni non sono necessario essere uguali. Il numero di elementi in una determinata dimensione può cambiare durante l'assegnazione.  
  
-   **Tipi di elemento.** Devono disporre di entrambe le matrici *tipo di riferimento* devono avere entrambe le matrici o gli elementi *tipo di valore* elementi. Per altre informazioni, vedere [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Se entrambe le matrici sono elementi di tipo valore, i tipi di dati elemento devono essere esattamente lo stesso. L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi in una matrice del tipo di base di tale `Enum`.  
  
    -   Se entrambe le matrici hanno riferimenti a elementi di tipo, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione. In questo caso, le due matrici hanno la stessa relazione di ereditarietà dei rispettivi elementi. Questa operazione viene definita *covarianza di matrici*.  
  
 Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o le classificazioni non sono uguali. È possibile aggiungere al codice per assicurarsi che le matrici sono compatibili prima di tentare un'assegnazione di gestione degli errori. È anche possibile usare la [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) parola chiave se si desidera evitare di generare un'eccezione.  
  
## <a name="see-also"></a>Vedere anche
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
