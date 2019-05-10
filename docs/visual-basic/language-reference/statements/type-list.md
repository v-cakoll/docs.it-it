---
title: Elenco dei tipi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: aae9135207bbd3f9d0cc7c072e423a50902c372a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751508"
---
# <a name="type-list-visual-basic"></a>Elenco dei tipi (Visual Basic)

Specifica la *parametri di tipo* per una *generico* elemento di programmazione. Più parametri sono separati da virgole. Di seguito è la sintassi per un parametro di tipo.

## <a name="syntax"></a>Sintassi

```
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`genericmodifier`|Facoltativo. Può essere utilizzato solo in interfacce e delegati generici. È possibile dichiarare un tipo covariante usando la [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) parola chiave o controvariante usando la [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) (parola chiave). Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Obbligatorio. Nome del parametro di tipo. Questo è un segnaposto, da sostituire con un tipo definito dall'argomento di tipo corrispondente.|
|`constraintlist`|Facoltativo. Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename`. Se si dispone di più vincoli, racchiuderli tra parentesi graffe (`{ }`) e separarle con virgole. È necessario introdurre l'elenco di vincoli con la [come](../../../visual-basic/language-reference/statements/as-clause.md) (parola chiave). Si utilizza `As` una sola volta, all'inizio dell'elenco.|

## <a name="remarks"></a>Note

Ogni elemento di programmazione generica deve accettare almeno un parametro di tipo. Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico. È possibile definire una classe generica, struttura, interfaccia, routine o delegato.

Per altre informazioni sui casi in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Per altre informazioni sui nomi dei parametri di tipo, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Regole

- **Parentesi.** Se si fornisce un elenco di parametri di tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Si utilizza `Of` una sola volta, all'inizio dell'elenco.

- **Vincoli.** Un elenco delle *vincoli* su un tipo di parametro può includere gli elementi seguenti in qualsiasi combinazione:

  - Numero qualsiasi di interfacce. Il tipo specificato deve implementare tutte le interfacce in questo elenco.

  - Al massimo una classe. Il tipo specificato deve ereditare da quella classe.

  - Parola chiave `New`. Il tipo fornito deve esporre un costruttore senza parametri accessibile il tipo generico. Ciò è utile se si vincola un parametro di tipo da una o più interfacce. Un tipo che implementa le interfacce non necessariamente espone un costruttore e a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.

  - Entrambi i `Class` parola chiave o il `Structure` (parola chiave). Il `Class` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento tipo passato da un tipo riferimento, ad esempio una stringa, matrice o delegato, o un oggetto creato da una classe. Il `Structure` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento tipo passato sia un tipo valore, ad esempio una struttura, enumerazione o tipo di dati di tipo. Non è possibile includere `Class` e `Structure` nello stesso `constraintlist`.

  Il tipo specificato deve soddisfare tutti i requisiti inclusi in `constraintlist`.

  Vincoli su ogni parametro di tipo sono indipendenti dai vincoli su altri parametri di tipo.

## <a name="behavior"></a>Comportamento

- **Sostituzione in fase di compilazione.** Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo. Il compilatore Visual Basic sostituisce il tipo specificato per tutte le occorrenze di `typename` all'interno dell'elemento generico.

- **Assenza di vincoli.** Se non si specifica alcun vincolo su un parametro di tipo, quest'ultima è limitato a operazioni e ai membri supportati dal [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) per tale parametro di tipo.

## <a name="example"></a>Esempio

Nell'esempio seguente illustra una struttura di definizione di una classe di dizionari generici, tra cui una funzione di base per aggiungere una nuova voce al dizionario.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Esempio

Poiché `dictionary` è generico, il codice che lo utilizza può creare un'ampia gamma di oggetti da quest'ultimo, ciascuno con le stesse funzionalità ma che agiscono su un tipo di dati diversi. L'esempio seguente mostra una riga di codice che crea una `dictionary` dell'oggetto con `String` voci e `Integer` chiavi.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Esempio

Nell'esempio seguente illustra la definizione di struttura equivalente generata dall'esempio precedente.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [Operatore New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
