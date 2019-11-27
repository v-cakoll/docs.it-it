---
title: Istruzione Const
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 1411e019058e7aac8249b7a50ecd295885a74177
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354132"
---
# <a name="const-statement-visual-basic"></a>Istruzione Const (Visual Basic)

Dichiara e definisce una o più costanti.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a>Parti

`attributelist`  
Facoltativa. Elenco di attributi che si applicano a tutte le costanti dichiarate in questa istruzione. Vedere l' [elenco degli attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi angolari ("`<`" e "`>`").

`accessmodifier`  
Facoltativa. Usare questa funzione per specificare quale codice può accedere a queste costanti. Può essere [public](../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [private](../../../visual-basic/language-reference/modifiers/private.md)o [private protected](../../language-reference/modifiers/private-protected.md).

`Shadows`  
Facoltativa. Usare questa classe per dichiarare e nascondere un elemento di programmazione in una classe base. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`constantlist`  
Obbligatoria. Elenco di costanti dichiarate in questa istruzione.

`constant` `[ ,` `constant` `... ]`

Ogni `constant` presenta la sintassi e le parti seguenti:

`constantname` `[ As` `datatype` `] =` `initializer`

|Parte|Descrizione|
|----------|-----------------|
|`constantname`|Obbligatoria. Nome della costante. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`datatype`|Obbligatorio se `Option Strict` è `On`. Tipo di dati della costante.|
|`initializer`|Obbligatoria. Espressione valutata in fase di compilazione e assegnata alla costante.|

## <a name="remarks"></a>Note

Se si dispone di un valore che non cambia mai nell'applicazione, è possibile definire una costante denominata e utilizzarla al posto di un valore letterale. Un nome è più facile da ricordare rispetto a un valore. È possibile definire la costante una sola volta e usarla in molte posizioni nel codice. Se in una versione successiva è necessario ridefinire il valore, l'istruzione `Const` è l'unica posizione necessaria per apportare una modifica.

È possibile utilizzare `Const` solo a livello di modulo o di procedura. Ciò significa che il *contesto di dichiarazione* per una variabile deve essere una classe, una struttura, un modulo, una procedura o un blocco e non può essere un file di origine, uno spazio dei nomi o un'interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Le costanti locali (all'interno di una procedura) utilizzano per impostazione predefinita l'accesso pubblico e non è possibile usare alcun modificatore di accesso. Le costanti membro della classe e del modulo (all'esterno di qualsiasi routine) per impostazione predefinita è l'accesso privato e le costanti membro della struttura vengono predefinite per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso.

## <a name="rules"></a>Regole

- **Contesto di dichiarazione.** Una costante dichiarata a livello di modulo, all'esterno di qualsiasi routine, è una *costante membro*; si tratta di un membro della classe, della struttura o del modulo che lo dichiara.

  Una costante dichiarata a livello di routine è una *costante locale*. è locale per la routine o il blocco che lo dichiara.

- **Attributi.** È possibile applicare attributi solo a costanti membro, non a costanti locali. Un attributo fornisce informazioni ai metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le costanti locali.

- **Modificatori.** Per impostazione predefinita, tutte le costanti sono `Shared`, `Static`e `ReadOnly`. Non è possibile usare una di queste parole chiave quando si dichiara una costante.

  A livello di procedura, non è possibile usare `Shadows` o alcun modificatore di accesso per dichiarare costanti locali.

- **Più costanti.** È possibile dichiarare più costanti nella stessa istruzione di dichiarazione, specificando la parte `constantname` per ciascuna di esse. Più costanti sono separate da virgole.

## <a name="data-type-rules"></a>Regole del tipo di dati

- **Tipi di dati.** L'istruzione `Const` può dichiarare il tipo di dati di una variabile. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione.

- **Tipo predefinito.** Se non si specifica `datatype`, la costante accetta il tipo di dati di `initializer`. Se si specificano sia `datatype` che `initializer`, il tipo di dati di `initializer` deve essere convertibile in `datatype`. Se non è presente né `datatype` né `initializer`, il tipo di dati predefinito è `Object`.

- **Tipi diversi.** È possibile specificare tipi di dati diversi per costanti diverse utilizzando una clausola `As` separata per ogni variabile dichiarata. Tuttavia, non è possibile dichiarare più costanti in modo che siano dello stesso tipo utilizzando una clausola `As` comune.

- **Inizializzazione.** È necessario inizializzare il valore di ogni costante in `constantlist`. Usare `initializer` per fornire un'espressione da assegnare alla costante. L'espressione può essere costituita da qualsiasi combinazione di valori letterali, altre costanti già definite e membri di enumerazione già definiti. Per combinare tali elementi, è possibile utilizzare operatori aritmetici e logici.

  Non è possibile usare variabili o funzioni in `initializer`. È tuttavia possibile usare parole chiave di conversione, ad esempio `CByte` e `CShort`. È inoltre possibile utilizzare `AscW` se viene chiamato con un argomento `String` o `Char` costante, dal momento che può essere valutato in fase di compilazione.

## <a name="behavior"></a>Comportamento

- **Ambito.** Le costanti locali sono accessibili solo dall'interno della procedura o del blocco. Le costanti membro sono accessibili da qualsiasi punto all'interno della classe, della struttura o del modulo.

- **Qualificazione.** Il codice esterno a una classe, una struttura o un modulo deve qualificare il nome di una costante membro con il nome della classe, della struttura o del modulo. Il codice esterno a una procedura o a un blocco non può fare riferimento alle costanti locali all'interno di tale procedura o blocco.

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l'istruzione `Const` per dichiarare le costanti da utilizzare al posto dei valori letterali.

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a>Esempio

Se si definisce una costante con tipo di dati `Object`, il compilatore Visual Basic lo assegna al tipo di `initializer`anziché `Object`. Nell'esempio seguente, la costante `naturalLogBase` dispone del tipo di runtime `Decimal`.

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

Nell'esempio precedente viene usato il metodo <xref:System.Type.ToString%2A> sull'oggetto <xref:System.Type> restituito dall' [operatore GetType](../../../visual-basic/language-reference/operators/gettype-operator.md), perché non è possibile convertire <xref:System.Type> in `String` con `CStr`.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Costanti ed enumerazioni](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
