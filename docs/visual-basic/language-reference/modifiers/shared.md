---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: bc63de4bda1e8e605e25fbe293686c187dd4d005
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290993"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)

Specifica che uno o più elementi di programmazione dichiarati sono associati a una classe o a una struttura di grandi dimensioni e non a un'istanza specifica della classe o della struttura.

## <a name="when-to-use-shared"></a>Quando usare Shared

La condivisione di un membro di una classe o di una struttura lo rende disponibile per ogni istanza, anziché *non condivisa*, in cui ogni istanza mantiene la propria copia. Questa operazione è utile, ad esempio, se il valore di una variabile viene applicato all'intera applicazione. Se si dichiara tale variabile come `Shared` , tutte le istanze accedono allo stesso percorso di archiviazione e se un'istanza modifica il valore della variabile, tutte le istanze accedono al valore aggiornato.

La condivisione non modifica il livello di accesso di un membro. Un membro di una classe, ad esempio, può essere condiviso e privato (accessibile solo dall'interno della classe) o non condiviso e pubblico. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Regole

- **Contesto della dichiarazione. ** Si può usare `Shared` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per un `Shared` elemento deve essere una classe o una struttura e non può essere un file di origine, uno spazio dei nomi o una procedura.

- **Modificatori combinati.** Non è possibile specificare `Shared` insieme a [override](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)o [static](../../../visual-basic/language-reference/modifiers/static.md) nella stessa dichiarazione.

- **Accesso.** Per accedere a un elemento condiviso, è necessario qualificarlo con il nome della classe o della struttura, non con il nome della variabile di un'istanza specifica della classe o della struttura. Non è nemmeno necessario creare un'istanza di una classe o di una struttura per accedere ai relativi membri condivisi.

     Nell'esempio seguente viene chiamata la procedura condivisa <xref:System.Double.IsNaN%2A> esposta dalla <xref:System.Double> struttura.

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- **Condivisione implicita.** Non è possibile usare il `Shared` modificatore in un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md), ma le costanti sono implicitamente condivise. Analogamente, non è possibile dichiarare un membro di un modulo o un'interfaccia come `Shared` , ma sono implicitamente condivisi.

## <a name="behavior"></a>Comportamento

- **Archiviazione.** Una variabile o un evento condiviso viene archiviato in memoria una sola volta, indipendentemente dal numero di istanze create dalla classe o dalla struttura. Analogamente, una routine o una proprietà condivisa include un solo set di variabili locali.

- **Accesso tramite una variabile di istanza.** È possibile accedere a un elemento condiviso qualificando il nome di una variabile che contiene un'istanza specifica della classe o della struttura. Sebbene questo in genere funzioni come previsto, il compilatore genera un messaggio di avviso e rende l'accesso tramite la classe o il nome della struttura anziché la variabile.

- **Accesso tramite un'espressione di istanza.** Se si accede a un elemento condiviso tramite un'espressione che restituisce un'istanza della relativa classe o struttura, il compilatore consente di accedere tramite il nome della classe o della struttura anziché di valutare l'espressione. Ciò produce risultati imprevisti se si desidera che l'espressione esegua altre azioni e restituisca l'istanza. Questa condizione è illustrata nell'esempio seguente.
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     Nell'esempio precedente, il compilatore genera un messaggio di avviso entrambe le volte che il codice accede alla proprietà condivisa `Total` tramite un'istanza. In ogni caso rende l'accesso direttamente tramite la classe `ShareTotal` e non usa alcuna istanza. Nel caso della chiamata prevista alla procedura `ReturnClass` , ciò significa che non viene anche generata una chiamata a `ReturnClass` , quindi non viene eseguita l'azione aggiuntiva di visualizzazione della funzione "ReturnClass () chiamata".

Il modificatore `Shared` può essere usato nei contesti seguenti:

- [Istruzione Dim](../statements/dim-statement.md)
- [Istruzione Event](../statements/event-statement.md)
- [Istruzione Function](../statements/function-statement.md)
- [Operator Statement](../operator-statement.md)
- [Property Statement](../property-statement.md)
- [Istruzione Sub](../sub-statement.md)
  
## <a name="see-also"></a>Vedere anche

- [Shadows](shadows.md)
- [Statico](static.md)
- [Durata in Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
