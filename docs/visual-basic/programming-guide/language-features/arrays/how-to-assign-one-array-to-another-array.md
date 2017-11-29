---
title: 'Procedura: assegnare una matrice a un''altra matrice (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0dd2d678bbfdeaa6b12b5b5a4f69d0fbca8c1944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Procedura: assegnare una matrice a un'altra matrice (Visual Basic)
Poiché le matrici sono oggetti, è possibile utilizzare le istruzioni di assegnazione, come altri tipi di oggetto. Una variabile di matrice contiene un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di classificazione e la lunghezza e un'assegnazione di copia solo l'indicatore di misura.  
  
### <a name="to-assign-one-array-to-another-array"></a>Per assegnare una matrice a un'altra matrice  
  
1.  Verificare che le due matrici abbiano la stessa classificazione (numero di dimensioni) e i tipi di dati compatibile.  
  
2.  Utilizzare un'istruzione di assegnazione standard per assegnare l'array di origine alla matrice di destinazione. Non seguono il nome di una matrice con parentesi.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 Quando si assegna una matrice a un altro, si applicano le regole seguenti:  
  
-   **Numeri di dimensioni uguali.** La classificazione (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.  
  
     Purché le classificazioni di due matrici sono uguali, le dimensioni non è necessario essere uguale. Il numero di elementi in una determinata dimensione può cambiare durante l'assegnazione.  
  
-   **Tipi di elemento.** Devono disporre di entrambe le matrici *tipo di riferimento* elementi o entrambe le matrici devono disporre *tipo di valore* elementi. Per ulteriori informazioni, vedere [tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Se entrambe le matrici sono elementi del tipo di valore, i tipi di elemento di dati devono essere esattamente lo stesso. L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi in una matrice del tipo di base di tale `Enum`.  
  
    -   Se entrambe le matrici hanno riferimento a elementi di tipo, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione. In questo caso, le due matrici hanno la stessa relazione di ereditarietà dei rispettivi elementi. Si tratta di *covarianza*.  
  
 Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o le classificazioni sono uguali. È possibile aggiungere il codice per assicurarsi che le matrici sono compatibili prima di tentare un'assegnazione di gestione degli errori. È inoltre possibile utilizzare il [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) (parola chiave), se si desidera evitare di generare un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
