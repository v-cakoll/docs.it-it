---
title: Variabile oggetto o variabile del blocco With non impostata
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040550"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variabile oggetto o variabile del blocco With non impostata
Viene fatto riferimento a una variabile oggetto non valida.   L'errore può essere determinato da numerose cause:

- Una variabile è stata dichiarata senza specificare un tipo. Se una variabile viene dichiarata senza specificare un tipo, il valore predefinito `Object`è Type.

    Ad esempio, una `Dim x` variabile dichiarata con sarebbe di tipo `Object;` una variabile dichiarata con `Dim x As String` sarebbe `String`di tipo.

    > [!TIP]
    > L' `Option Strict` istruzione impedisce la tipizzazione implicita che restituisce un `Object` tipo. Se si omette il tipo, si verificherà un errore in fase di compilazione. Vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).

- Si sta provando a fare riferimento a un oggetto che è stato impostato `Nothing`su.

- Si sta tentando di accedere a un elemento di una variabile di matrice non dichiarata correttamente.

    Ad esempio, una matrice dichiarata come `products() As String` attiverà l'errore se si tenta di fare riferimento a un elemento della matrice. `products(3) = "Widget"` La matrice non ha elementi e viene considerata come un oggetto.

- Si sta tentando di accedere al codice all' `With...End With` interno di un blocco prima che il blocco sia stato inizializzato.   Un `With...End With` blocco deve essere inizializzato tramite l'esecuzione `With` del punto di ingresso dell'istruzione.

> [!NOTE]
> Nelle versioni precedenti di Visual Basic o VBA questo errore è stato attivato anche assegnando un valore a una variabile senza usare la `Set` parola chiave (`x = "name"` anziché `Set x = "name"`). La `Set` parola chiave non è più valida in Visual Basic .NET.

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Impostare `Option Strict` su`On` aggiungendo il codice seguente all'inizio del file:

    ```vb
    Option Strict On
    ```

    Quando si esegue il progetto, nel **Elenco errori** viene visualizzato un errore del compilatore per qualsiasi variabile specificata senza un tipo.

2. Se non si vuole abilitare `Option Strict`, cercare nel codice qualsiasi variabile specificata senza un tipo (`Dim x` anziché `Dim x As String`) e aggiungere il tipo desiderato alla dichiarazione.

3. Assicurarsi che non si faccia riferimento a una variabile oggetto che è stata impostata su `Nothing`.  Cercare il codice per la parola `Nothing`chiave e modificare il codice in modo che l'oggetto non sia impostato `Nothing` su fino a quando non viene fatto riferimento a esso.

4. Verificare che le variabili di matrice siano dimensionate prima di accedervi. È possibile assegnare una dimensione alla prima creazione della matrice (`Dim x(5) As String` `Dim x() As String`anziché) oppure utilizzare la `ReDim` parola chiave per impostare le dimensioni della matrice prima di accedervi per la prima volta.

5. Verificare che il `With` blocco venga inizializzato eseguendo il punto `With` di ingresso dell'istruzione.

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
