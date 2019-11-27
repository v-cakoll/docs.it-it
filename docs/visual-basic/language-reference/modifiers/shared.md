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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349122"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono associati a una classe o a una struttura di grandi dimensioni e non a un'istanza specifica della classe o della struttura.  
  
## <a name="remarks"></a>Note  
  
## <a name="when-to-use-shared"></a>Quando usare Shared  
 La condivisione di un membro di una classe o di una struttura lo rende disponibile a ogni istanza, anziché non *condiviso*, in cui ogni istanza mantiene la propria copia. Questa operazione è utile, ad esempio, se il valore di una variabile viene applicato all'intera applicazione. Se si dichiara la variabile da `Shared`, tutte le istanze accedono allo stesso percorso di archiviazione e se un'istanza modifica il valore della variabile, tutte le istanze accedono al valore aggiornato.  
  
 La condivisione non modifica il livello di accesso di un membro. Un membro di una classe, ad esempio, può essere condiviso e privato (accessibile solo dall'interno della classe) oppure non condiviso e pubblico. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Contesto di dichiarazione.** Si può usare `Shared` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per un elemento di `Shared` deve essere una classe o una struttura e non può essere un file di origine, uno spazio dei nomi o una procedura.  
  
- **Modificatori combinati.** Non è possibile specificare `Shared` insieme a [override](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)o [static](../../../visual-basic/language-reference/modifiers/static.md) nella stessa dichiarazione.  
  
- **Accesso.** Per accedere a un elemento condiviso, è necessario qualificarlo con il nome della classe o della struttura, non con il nome della variabile di un'istanza specifica della classe o della struttura. Non è nemmeno necessario creare un'istanza di una classe o di una struttura per accedere ai relativi membri condivisi.  
  
     Nell'esempio seguente viene chiamata la stored procedure condivisa <xref:System.Double.IsNaN%2A> esposta dalla struttura di <xref:System.Double>.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- **Condivisione implicita.** Non è possibile usare il modificatore `Shared` in un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md), ma le costanti sono implicitamente condivise. Analogamente, non è possibile dichiarare un membro di un modulo o un'interfaccia da `Shared`, ma sono condivisi in modo implicito.  
  
## <a name="behavior"></a>Comportamento  
  
- **Archiviazione.** Una variabile o un evento condiviso viene archiviato in memoria una sola volta, indipendentemente dal numero di istanze create dalla classe o dalla struttura. Analogamente, una routine o una proprietà condivisa include un solo set di variabili locali.  
  
- **Accesso tramite una variabile di istanza.** È possibile accedere a un elemento condiviso qualificando il nome di una variabile che contiene un'istanza specifica della classe o della struttura. Sebbene questo in genere funzioni come previsto, il compilatore genera un messaggio di avviso e rende l'accesso tramite la classe o il nome della struttura anziché la variabile.  
  
- **Accesso tramite un'espressione di istanza.** Se si accede a un elemento condiviso tramite un'espressione che restituisce un'istanza della relativa classe o struttura, il compilatore consente di accedere tramite il nome della classe o della struttura anziché di valutare l'espressione. Ciò produce risultati imprevisti se si desidera che l'espressione esegua altre azioni e restituisca l'istanza. Ciò è illustrato nell'esempio seguente.  
  
    ```vb
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
  
     Nell'esempio precedente, il compilatore genera un messaggio di avviso entrambe le volte che il codice accede alla variabile condivisa `total` tramite un'istanza. In ogni caso, l'accesso viene reso direttamente tramite la classe `shareTotal` e non usa alcuna istanza. Nel caso della chiamata prevista alla procedura `returnClass`, ciò significa che non genera neanche una chiamata a `returnClass`, quindi non viene eseguita l'azione aggiuntiva di visualizzazione della funzione "returnClass () chiamata".  
  
 Il modificatore `Shared` può essere usato nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
