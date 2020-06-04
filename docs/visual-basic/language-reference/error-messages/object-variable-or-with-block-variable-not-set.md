---
title: Variabile oggetto o variabile del blocco With non impostata
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: d1778e2bb58d32e976f10b3fba1637918278d36e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409283"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variabile oggetto o variabile del blocco With non impostata
Viene fatto riferimento a una variabile oggetto non valida.   L'errore può essere determinato da numerose cause:

- Una variabile è stata dichiarata senza specificare un tipo. Se una variabile viene dichiarata senza specificare un tipo, il valore predefinito è Type `Object` .

    Ad esempio, una variabile dichiarata con `Dim x` sarebbe di tipo `Object;` una variabile dichiarata con `Dim x As String` sarebbe di tipo `String` .

    > [!TIP]
    > L' `Option Strict` istruzione impedisce la tipizzazione implicita che restituisce un `Object` tipo. Se si omette il tipo, si verificherà un errore in fase di compilazione. Vedere [istruzione Option Strict](../statements/option-strict-statement.md).

- Si sta provando a fare riferimento a un oggetto che è stato impostato su `Nothing` .

- Si sta tentando di accedere a un elemento di una variabile di matrice non dichiarata correttamente.

    Ad esempio, una matrice dichiarata come `products() As String` attiverà l'errore se si tenta di fare riferimento a un elemento della matrice `products(3) = "Widget"` . La matrice non ha elementi e viene considerata come un oggetto.

- Si sta tentando di accedere al codice all'interno di un `With...End With` blocco prima che il blocco sia stato inizializzato.   Un `With...End With` blocco deve essere inizializzato tramite l'esecuzione del `With` punto di ingresso dell'istruzione.

> [!NOTE]
> Nelle versioni precedenti di Visual Basic o VBA questo errore è stato attivato anche assegnando un valore a una variabile senza usare la `Set` parola chiave ( `x = "name"` anziché `Set x = "name"` ). La `Set` parola chiave non è più valida in Visual Basic .NET.

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Impostare `Option Strict` su aggiungendo `On` il codice seguente all'inizio del file:

    ```vb
    Option Strict On
    ```

    Quando si esegue il progetto, nel **Elenco errori** viene visualizzato un errore del compilatore per qualsiasi variabile specificata senza un tipo.

2. Se non si vuole abilitare `Option Strict` , cercare nel codice qualsiasi variabile specificata senza un tipo ( `Dim x` anziché `Dim x As String` ) e aggiungere il tipo desiderato alla dichiarazione.

3. Assicurarsi che non si faccia riferimento a una variabile oggetto che è stata impostata su `Nothing` .  Cercare il codice per la parola chiave `Nothing` e modificare il codice in modo che l'oggetto non sia impostato su fino a quando non viene `Nothing` fatto riferimento a esso.

4. Verificare che le variabili di matrice siano dimensionate prima di accedervi. È possibile assegnare una dimensione alla prima creazione della matrice ( `Dim x(5) As String` anziché `Dim x() As String` ) oppure utilizzare la `ReDim` parola chiave per impostare le dimensioni della matrice prima di accedervi per la prima volta.

5. Verificare che il `With` blocco venga inizializzato eseguendo il `With` punto di ingresso dell'istruzione.

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabili oggetto](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [Istruzione ReDim](../statements/redim-statement.md)
- [Istruzione With...End With](../statements/with-end-with-statement.md)
