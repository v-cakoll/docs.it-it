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
ms.openlocfilehash: a0d489684b8f98e871211e6d0d95d42284275954
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582901"
---
# <a name="type-list-visual-basic"></a>Elenco dei tipi (Visual Basic)

Specifica i *parametri di tipo* per un elemento di programmazione *generico* . Più parametri sono separati da virgole. Di seguito è riportata la sintassi per un parametro di tipo.

## <a name="syntax"></a>Sintassi

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`genericmodifier`|Parametro facoltativo. Può essere usato solo in interfacce e delegati generici. È possibile dichiarare un tipo covariante usando la parola chiave [out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) o controvariante usando la parola chiave [in](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) . Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Obbligatorio. Nome del parametro di tipo. Si tratta di un segnaposto, che deve essere sostituito da un tipo definito fornito dall'argomento di tipo corrispondente.|
|`constraintlist`|Parametro facoltativo. Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename`. Se sono presenti più vincoli, racchiuderli tra parentesi graffe (`{ }`) e separarli con virgole. È necessario introdurre l'elenco di vincoli con la parola chiave [As](../../../visual-basic/language-reference/statements/as-clause.md) . Usare `As` una sola volta, all'inizio dell'elenco.|

## <a name="remarks"></a>Note

Ogni elemento di programmazione generico deve assumere almeno un parametro di tipo. Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico. È possibile definire una classe, una struttura, un'interfaccia, una routine o un delegato generico.

Per ulteriori informazioni sul momento in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Per ulteriori informazioni sui nomi dei parametri di tipo, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Regole

- **Parentesi.** Se si fornisce un elenco [di parametri di](../../../visual-basic/language-reference/statements/of-clause.md) tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con la parola chiave of. Usare `Of` una sola volta, all'inizio dell'elenco.

- **Vincoli.** Un elenco di *vincoli* in un parametro di tipo può includere gli elementi seguenti in qualsiasi combinazione:

  - Un numero qualsiasi di interfacce. Il tipo fornito deve implementare ogni interfaccia in questo elenco.

  - Al massimo una classe. Il tipo specificato deve ereditare da quella classe.

  - Parola chiave `New`. Il tipo fornito deve esporre un costruttore senza parametri a cui il tipo generico può accedere. Questa operazione è utile se si vincola un parametro di tipo in base a una o più interfacce. Un tipo che implementa le interfacce non espone necessariamente un costruttore e, a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.

  - Parola chiave `Class` o parola chiave `Structure`. La parola chiave `Class` vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo riferimento, ad esempio una stringa, una matrice o un delegato, oppure un oggetto creato da una classe. La parola chiave `Structure` vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo valore, ad esempio una struttura, un'enumerazione o un tipo di dati elementare. Non è possibile includere sia `Class` che `Structure` nello stesso `constraintlist`.

  Il tipo fornito deve soddisfare ogni requisito incluso in `constraintlist`.

  I vincoli su ogni parametro di tipo sono indipendenti dai vincoli di altri parametri di tipo.

## <a name="behavior"></a>Comportamento

- **Sostituzione in fase di compilazione.** Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo. Il compilatore Visual Basic sostituisce il tipo fornito per ogni occorrenza di `typename` all'interno dell'elemento generico.

- **Assenza di vincoli.** Se non si specifica alcun vincolo per un parametro di tipo, il codice è limitato alle operazioni e ai membri supportati dal [tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md) per quel parametro di tipo.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una definizione di scheletro di una classe di dizionario generica, inclusa una funzione Skeleton per aggiungere una nuova voce al dizionario.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Esempio

Poiché `dictionary` è generico, il codice che lo usa può creare una varietà di oggetti, ognuno dei quali ha la stessa funzionalità ma agisce su un tipo di dati diverso. Nell'esempio seguente viene illustrata una riga di codice che crea un oggetto `dictionary` con `String` le voci e le chiavi di `Integer`.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata la definizione di scheletro equivalente generata dall'esempio precedente.

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
