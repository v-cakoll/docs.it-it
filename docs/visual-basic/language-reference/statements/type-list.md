---
title: Type List
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
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412988"
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
|`genericmodifier`|Facoltativa. Può essere usato solo in interfacce e delegati generici. È possibile dichiarare un tipo covariante usando la parola chiave [out](../modifiers/out-generic-modifier.md) o controvariante usando la parola chiave [in](../modifiers/in-generic-modifier.md) . Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Obbligatorio. Nome del parametro di tipo. Si tratta di un segnaposto, che deve essere sostituito da un tipo definito fornito dall'argomento di tipo corrispondente.|
|`constraintlist`|Facoltativa. Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename` . Se sono presenti più vincoli, racchiuderli tra parentesi graffe ( `{ }` ) e separarli con virgole. È necessario introdurre l'elenco di vincoli con la parola chiave [As](as-clause.md) . Si usa `As` una sola volta, all'inizio dell'elenco.|

## <a name="remarks"></a>Commenti

Ogni elemento di programmazione generico deve assumere almeno un parametro di tipo. Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico. È possibile definire una classe, una struttura, un'interfaccia, una routine o un delegato generico.

Per ulteriori informazioni sul momento in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md). Per ulteriori informazioni sui nomi dei parametri di tipo, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Regole

- **Parentesi.** Se si fornisce un elenco [di parametri di](of-clause.md) tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con la parola chiave of. Si usa `Of` una sola volta, all'inizio dell'elenco.

- **Vincoli.** Un elenco di *vincoli* in un parametro di tipo può includere gli elementi seguenti in qualsiasi combinazione:

  - Un numero qualsiasi di interfacce. Il tipo fornito deve implementare ogni interfaccia in questo elenco.

  - Al massimo una classe. Il tipo specificato deve ereditare da quella classe.

  - Parola chiave `New`. Il tipo fornito deve esporre un costruttore senza parametri a cui il tipo generico può accedere. Questa operazione è utile se si vincola un parametro di tipo in base a una o più interfacce. Un tipo che implementa le interfacce non espone necessariamente un costruttore e, a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.

  - `Class`Parola chiave o `Structure` parola chiave. La `Class` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo riferimento, ad esempio una stringa, una matrice o un delegato, oppure un oggetto creato da una classe. La `Structure` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo valore, ad esempio una struttura, un'enumerazione o un tipo di dati elementare. Non è possibile includere sia `Class` che `Structure` nello stesso `constraintlist` .

  Il tipo fornito deve soddisfare ogni requisito incluso in `constraintlist` .

  I vincoli su ogni parametro di tipo sono indipendenti dai vincoli di altri parametri di tipo.

## <a name="behavior"></a>Comportamento

- **Sostituzione in fase di compilazione.** Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo. Il compilatore Visual Basic sostituisce il tipo fornito per ogni occorrenza di `typename` all'interno dell'elemento generico.

- **Assenza di vincoli.** Se non si specifica alcun vincolo per un parametro di tipo, il codice è limitato alle operazioni e ai membri supportati dal [tipo di dati Object](../data-types/object-data-type.md) per quel parametro di tipo.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una definizione di scheletro di una classe di dizionario generica, inclusa una funzione Skeleton per aggiungere una nuova voce al dizionario.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Esempio

Poiché `dictionary` è generico, il codice che lo usa può creare un'ampia gamma di oggetti, ognuno dei quali ha la stessa funzionalità ma agisce su un tipo di dati diverso. Nell'esempio seguente viene illustrata una riga di codice che crea un `dictionary` oggetto con le `String` voci e le `Integer` chiavi.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata la definizione di scheletro equivalente generata dall'esempio precedente.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Di](of-clause.md)
- [Operatore New](../operators/new-operator.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Object Data Type](../data-types/object-data-type.md)
- [Istruzione Function](function-statement.md)
- [Istruzione Structure](structure-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Procedura: Usare una classe generica](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
