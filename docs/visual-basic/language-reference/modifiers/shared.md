---
title: Shared (Visual Basic)
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
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604549"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono associati una classe o una struttura e non con una specifica istanza della classe o struttura.  
  
## <a name="remarks"></a>Note  
  
## <a name="when-to-use-shared"></a>Quando utilizzare condiviso  
 Quando un membro di una classe o struttura rende disponibili per ogni istanza, anziché *non condivisa*, in cui ogni istanza mantiene la propria copia. Questo è utile, ad esempio, se il valore di una variabile viene applicato all'intera applicazione. Se si dichiara la variabile `Shared`, quindi tutte le istanze accederanno stesso percorso di archiviazione e se un'istanza viene modificato il valore della variabile, tutte le istanze di accederanno al valore aggiornato.  
  
 La condivisione non modifica il livello di accesso di un membro. Ad esempio, un membro di classe può essere condivisi e privati (accessibili solo dall'interno della classe), o non condiviso e pubblico. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Si può usare `Shared` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `Shared` elemento deve essere una classe o struttura e non può essere un file di origine, lo spazio dei nomi o stored procedure.  
  
-   **Modificatori combinati.** Non è possibile specificare `Shared` con [esegue l'override](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), o [ Statico](../../../visual-basic/language-reference/modifiers/static.md) nella stessa dichiarazione.  
  
-   **L'accesso.** Accedere a un elemento condiviso qualificandola con il nome di classe o struttura, non con il nome della variabile di un'istanza specifica della relativa classe o struttura. Anche, non è necessario creare un'istanza di una classe o struttura per accedere ai relativi membri condivisi.  
  
     Nell'esempio seguente chiama la routine condivisa <xref:System.Double.IsNaN%2A> esposti dal <xref:System.Double> struttura.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Condivisione implicita.** Non è possibile utilizzare il `Shared` modificatore in una [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md), ma le costanti sono condivise in modo implicito. Analogamente, non è possibile dichiarare un membro di un modulo o un'interfaccia di `Shared`, ma tali elementi vengono condivisi in modo implicito.  
  
## <a name="behavior"></a>Comportamento  
  
-   **spazio di archiviazione.** Una variabile condivisa o un evento viene archiviato in memoria una sola volta, indipendentemente dal numero di istanze create della relativa classe o struttura. Analogamente, una routine condivisa o la proprietà contiene un solo set di variabili locali.  
  
-   **L'accesso tramite una variabile di istanza.** È possibile accedere a un elemento condiviso qualificandola con il nome di una variabile che contiene un'istanza specifica della relativa classe o struttura. Sebbene questo in genere funziona come previsto, il compilatore genera un messaggio di avviso ed effettua l'accesso tramite il nome di classe o struttura anziché la variabile.  
  
-   **L'accesso tramite un'espressione di istanza.** Se si accede a un elemento condiviso tramite un'espressione che restituisce un'istanza della classe o struttura, il compilatore effettua l'accesso tramite il nome di classe o struttura invece di valutare l'espressione. Questo produce risultati imprevisti se si prevede l'espressione per eseguire altre operazioni, nonché a restituire l'istanza. Questa condizione è illustrata nell'esempio seguente.  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     Nell'esempio precedente, il compilatore genera un messaggio di avviso due volte il codice accede alla variabile condivisa `total` tramite un'istanza. In ogni caso effettua l'accesso direttamente tramite la classe `shareTotal` e non viene utilizzata alcuna istanza. Nel caso della chiamata alla procedura `returnClass`, ciò significa che non genera anche una chiamata a `returnClass`, pertanto non viene eseguita l'azione aggiuntiva di visualizzazione "Function returnClass () chiamata".  
  
 Il modificatore `Shared` può essere usato nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Static](../../../visual-basic/language-reference/modifiers/static.md)  
 [Durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
