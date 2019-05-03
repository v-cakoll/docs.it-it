---
title: Variabile oggetto o variabile del blocco With non impostata
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 766b95163f164ec76135b964115069b6855ceebf
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807877"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variabile oggetto o variabile del blocco With non impostata
Riferimento a una variabile oggetto non valido.   L'errore può essere determinato da numerose cause:

- Una variabile è stata dichiarata senza specificare un tipo. Se una variabile viene dichiarata senza specificare un tipo, per impostazione predefinita per digitare `Object`.

    Ad esempio, una variabile dichiarata con `Dim x` saranno di tipo `Object;` una variabile dichiarata con `Dim x As String` saranno di tipo `String`.

    > [!TIP]
    >  Il `Option Strict` istruzione la tipizzazione implicita che comporta un `Object` tipo. Se si omette il tipo, si verificherà un errore in fase di compilazione. Visualizzare [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).

- Si sta provando a fare riferimento a un oggetto che è stato impostato su `Nothing`.

- Si sta tentando di accedere a un elemento di una variabile di matrice che non è stata dichiarata in modo corretto.

    Ad esempio, una matrice dichiarata come `products() As String` attiveranno l'errore se si tenta di fare riferimento a un elemento della matrice `products(3) = "Widget"`. La matrice dispone di alcun elemento e viene considerata come un oggetto.

- Sta tentando di accedere a codice all'interno di un `With...End With` blocco prima che il blocco è stato inizializzato.   Oggetto `With...End With` blocco deve essere inizializzato mediante l'esecuzione di `With` punto di ingresso di istruzione.

> [!NOTE]
> Nelle versioni precedenti di Visual Basic o VBA questo errore è stato attivato anche assegnando un valore a una variabile senza usare la `Set` parola chiave (`x = "name"` invece di `Set x = "name"`). Il `Set` parola chiave non è più valido in Visual Basic .net.

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Impostare `Option Strict` a `On` aggiungendo il codice seguente all'inizio del file:

    ```vb
    Option Strict On
    ```

    Quando si esegue il progetto, verrà visualizzato un errore del compilatore nel **elenco errori** per qualsiasi variabile che è stata specificata senza un tipo.

2. Se non si vuole abilitare `Option Strict`, il codice per tutte le variabili che sono stati specificati senza un tipo di ricerca (`Dim x` invece di `Dim x As String`) e aggiungere il tipo desiderato alla dichiarazione.

3. Assicurarsi che invece non si fa riferimento a una variabile oggetto che è stata impostata su `Nothing`.  Eseguire ricerche nel codice per la parola chiave `Nothing`e modificare il codice in modo che l'oggetto non è impostato su `Nothing` fino a quando non dopo che si è fatto riferimento.

4. Assicurarsi che tutte le variabili di matrice vengono dimensionate prima di accedervi. È possibile assegnare una dimensione al momento della creazione della matrice (`Dim x(5) As String` invece di `Dim x() As String`), oppure usare il `ReDim` parola chiave per impostare le dimensioni della matrice prima che si accede.

5. Assicurarsi che il `With` blocco viene inizializzato tramite l'esecuzione di `With` punto di ingresso di istruzione.

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
