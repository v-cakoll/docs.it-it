---
title: Scope
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 1bee904996257474b7457b2aefb1f17d250933cb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410734"
---
# <a name="scope-in-visual-basic"></a>Ambito in Visual Basic

L' *ambito* di un elemento dichiarato è il set di tutto il codice che può farvi riferimento senza qualificarne il nome o renderlo disponibile tramite un' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md). Un elemento può avere un ambito a uno dei livelli seguenti:

|Level|Descrizione|
|-----------|-----------------|
|Ambito del blocco|Disponibile solo all'interno del blocco di codice in cui è dichiarata|
|Ambito procedura|Disponibile per tutto il codice all'interno della routine in cui è dichiarata|
|Ambito del modulo|Disponibile per tutto il codice all'interno del modulo, della classe o della struttura in cui è dichiarata|
|Ambito dello spazio dei nomi|Disponibile per tutto il codice nello spazio dei nomi in cui è dichiarato|

Questi livelli di avanzamento dell'ambito dal più piccolo (blocco) al più ampio (spazio dei nomi), dove l' *ambito più ristretto* indica il set di codice più piccolo che può fare riferimento all'elemento senza qualifica. Per ulteriori informazioni, vedere "livelli di ambito" in questa pagina.

## <a name="specifying-scope-and-defining-variables"></a>Specifica dell'ambito e definizione delle variabili

L'ambito di un elemento viene specificato quando lo si dichiara. L'ambito può dipendere dai fattori seguenti:

- Area (Block, procedure, modulo, classe o struttura) in cui viene dichiarato l'elemento

- Spazio dei nomi contenente la dichiarazione dell'elemento.

- Livello di accesso dichiarato per l'elemento

Prestare attenzione quando si definiscono le variabili con lo stesso nome ma con un ambito diverso, perché questa operazione può causare risultati imprevisti. Per altre informazioni, vedere [References to Declared Elements](references-to-declared-elements.md).

## <a name="levels-of-scope"></a>Livelli di ambito

Un elemento di programmazione è disponibile nell'area geografica in cui viene dichiarata. Tutto il codice nella stessa area può fare riferimento all'elemento senza qualificare il nome.

### <a name="block-scope"></a>Ambito del blocco

Un blocco è un set di istruzioni racchiuse tra istruzioni di inizializzazione e terminazione di dichiarazione, come le seguenti:

- `Do` e `Loop`

- `For`[ `Each` ] e`Next`

- `If` e `End If`

- `Select` e `End Select`

- `SyncLock` e `End SyncLock`

- `Try` e `End Try`

- `While` e `End While`

- `With` e `End With`

Se si dichiara una variabile all'interno di un blocco, è possibile utilizzarla solo all'interno di tale blocco. Nell'esempio seguente, l'ambito della variabile integer `cube` è il blocco tra e e `If` `End If` non è più possibile fare riferimento a quando l' `cube` esecuzione passa all'esterno del blocco.

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> Anche se l'ambito di una variabile è limitato a un blocco, la sua durata è ancora quella dell'intera procedura. Se durante la procedura si immette più di una volta il blocco, ogni variabile di blocco mantiene il valore precedente. Per evitare risultati imprevisti in tal caso, è consigliabile inizializzare le variabili di blocco all'inizio del blocco.

### <a name="procedure-scope"></a>Ambito procedura

Un elemento dichiarato all'interno di una routine non è disponibile all'esterno di tale procedura. Solo la routine che contiene la dichiarazione può usarla. Le variabili a questo livello sono note anche come *variabili locali*. Vengono dichiarati con l' [istruzione Dim](../../../language-reference/statements/dim-statement.md), con o senza la parola chiave [static](../../../language-reference/modifiers/static.md) .

La procedura e l'ambito del blocco sono strettamente correlati. Se si dichiara una variabile all'interno di una routine, ma all'esterno di qualsiasi blocco all'interno di tale procedura, è possibile considerare la variabile come avente un ambito di blocco, in cui il blocco è l'intera routine.

> [!NOTE]
> Tutti gli elementi locali, anche se sono `Static` variabili, sono privati della routine in cui vengono visualizzati. Non è possibile dichiarare alcun elemento utilizzando la parola chiave [public](../../../language-reference/modifiers/public.md) all'interno di una routine.

### <a name="module-scope"></a>Ambito del modulo

Per praticità, il *livello del modulo* a singolo termine si applica ugualmente a moduli, classi e strutture. È possibile dichiarare elementi a questo livello inserendo l'istruzione di dichiarazione all'esterno di qualsiasi routine o blocco, ma all'interno del modulo, della classe o della struttura.

Quando si crea una dichiarazione a livello di modulo, il livello di accesso scelto determina l'ambito. Lo spazio dei nomi che contiene il modulo, la classe o la struttura influiscono anche sull'ambito.

Gli elementi per i quali si dichiara il livello di accesso [privato](../../../language-reference/modifiers/private.md) sono disponibili per tutte le procedure del modulo, ma non per il codice in un modulo diverso. L' `Dim` istruzione a livello di modulo viene utilizzata per impostazione predefinita `Private` se non si utilizzano parole chiave del livello di accesso. Tuttavia, è possibile rendere più evidenti l'ambito e il livello di accesso utilizzando la `Private` parola chiave nell' `Dim` istruzione.

Nell'esempio seguente, tutte le routine definite nel modulo possono fare riferimento alla variabile di stringa `strMsg` . Quando viene chiamata la seconda procedura, viene visualizzato il contenuto della variabile stringa `strMsg` in una finestra di dialogo.

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a>Ambito dello spazio dei nomi

Se si dichiara un elemento a livello di modulo usando la parola chiave [Friend](../../../language-reference/modifiers/friend.md) o [public](../../../language-reference/modifiers/public.md) , diventa disponibile per tutte le routine in tutto lo spazio dei nomi in cui viene dichiarato l'elemento. Con la seguente modifica all'esempio precedente, `strMsg` è possibile fare riferimento alla variabile di stringa dal codice in qualsiasi punto dello spazio dei nomi della relativa dichiarazione.

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

Lo spazio dei nomi include spazi dei nomi annidati. Un elemento disponibile in uno spazio dei nomi è disponibile anche all'interno di qualsiasi spazio dei nomi annidato all'interno di tale spazio dei nomi.

Se il progetto non contiene alcuna [istruzione dello spazio dei nomi](../../../language-reference/statements/namespace-statement.md), tutti gli elementi del progetto si trova nello stesso spazio dei nomi. In questo caso, l'ambito dello spazio dei nomi può essere considerato come ambito del progetto. `Public`gli elementi in un modulo, una classe o una struttura sono disponibili anche per qualsiasi progetto che fa riferimento al progetto.

## <a name="choice-of-scope"></a>Scelta dell'ambito

Quando si dichiara una variabile, è necessario tenere presenti i punti seguenti quando si sceglie l'ambito.

### <a name="advantages-of-local-variables"></a>Vantaggi delle variabili locali

Le variabili locali rappresentano una scelta ottimale per qualsiasi tipo di calcolo temporaneo, per i motivi seguenti:

- **Evitare conflitti di nomi.** I nomi delle variabili locali non sono suscettibili ai conflitti. È ad esempio possibile creare diverse procedure contenenti una variabile denominata `intTemp` . Fino a quando ogni `intTemp` routine viene dichiarata come variabile locale, ogni procedura riconosce solo la propria versione di `intTemp` . Qualsiasi procedura può modificare il valore nel relativo oggetto locale `intTemp` senza influire sulle `intTemp` variabili in altre routine.

- **Consumo di memoria.** Le variabili locali utilizzano la memoria solo mentre è in esecuzione la relativa procedura. La memoria viene rilasciata quando la procedura viene restituita al codice chiamante. Al contrario, le variabili [condivise](../../../language-reference/modifiers/shared.md) e [statiche](../../../language-reference/modifiers/static.md) utilizzano risorse di memoria fino a quando l'applicazione non viene arrestata, quindi utilizzarle solo quando necessario. Le *variabili di istanza* utilizzano la memoria mentre la loro istanza continua a esistere, rendendole meno efficienti rispetto alle variabili locali, ma potenzialmente più efficienti delle `Shared` variabili o `Static` .

### <a name="minimizing-scope"></a>Riduzione dell'ambito

In generale, quando si dichiara una variabile o una costante, è consigliabile fare in modo che l'ambito sia più stretto possibile (l'ambito del blocco è il più piccolo). Questo consente di conservare la memoria e ridurre al minimo le probabilità che il codice faccia riferimento erroneamente alla variabile non corretta. Analogamente, è consigliabile dichiarare una variabile come [statica](../../../language-reference/modifiers/static.md) solo quando è necessario mantenerne il valore tra le chiamate di routine.

## <a name="see-also"></a>Vedere anche

- [Caratteristiche di elementi dichiarati](declared-element-characteristics.md)
- [Procedura: controllare l'ambito di una variabile](how-to-control-the-scope-of-a-variable.md)
- [Durata in Visual Basic](lifetime.md)
- [Livelli di accesso in Visual Basic](access-levels.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
