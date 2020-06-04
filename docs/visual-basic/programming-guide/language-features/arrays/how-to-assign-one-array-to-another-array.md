---
title: "Procedura: assegnare una matrice a un'altra matrice"
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: c38def1ba9f3720bc760d6f6e4264510c884c930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413079"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Procedura: assegnare una matrice a un'altra matrice (Visual Basic)

Poiché le matrici sono oggetti, è possibile usarle nelle istruzioni di assegnazione come altri tipi di oggetto. Una variabile di matrice include un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di rango e lunghezza e un'assegnazione copia solo questo puntatore.

### <a name="to-assign-one-array-to-another-array"></a>Per assegnare una matrice a un'altra matrice

1. Verificare che le due matrici abbiano lo stesso rango (numero di dimensioni) e tipi di dati degli elementi compatibili.

2. Utilizzare un'istruzione di assegnazione standard per assegnare la matrice di origine alla matrice di destinazione. Non seguire neanche il nome della matrice con le parentesi.

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

Quando si assegna una matrice a un'altra, si applicano le regole seguenti:

- **Corrispondenze di rango.** Il rango (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.

  Se le classificazioni delle due matrici sono uguali, le dimensioni non devono essere uguali. Il numero di elementi in una determinata dimensione può essere modificato durante l'assegnazione.

- **Tipi di elemento.** Entrambe le matrici devono avere elementi di *tipo riferimento* o entrambe le matrici devono avere elementi di *tipo valore* . Per altre informazioni, vedere [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).

  - Se entrambe le matrici hanno elementi di tipo valore, i tipi di dati degli elementi devono essere esattamente gli stessi. L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi a una matrice del tipo di base `Enum` .

  - Se entrambe le matrici hanno elementi di tipo riferimento, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione. In tal caso, le due matrici hanno la stessa relazione di ereditarietà dei relativi elementi. Questa operazione è denominata *covarianza di matrici*.

Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o se le classificazioni sono diverse. È possibile aggiungere la gestione degli errori al codice per assicurarsi che le matrici siano compatibili prima di tentare un'assegnazione. È anche possibile usare la parola chiave dell' [operatore TryCast](../../../language-reference/operators/trycast-operator.md) se si vuole evitare la generazione di un'eccezione.

## <a name="see-also"></a>Vedere anche

- [Matrici](index.md)
- [Risoluzione dei problemi relativi alle matrici](troubleshooting-arrays.md)
- [Istruzione Enum](../../../language-reference/statements/enum-statement.md)
- [Conversioni di matrice](../data-types/array-conversions.md)
