---
title: Istruzione Property (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332739"
---
# <a name="property-statement"></a>Property Statement

Dichiara il nome di una proprietà e le routine della proprietà usate per archiviare e recuperare il valore della proprietà.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>Parti

- `attributelist`

  facoltativo. Elenco degli attributi che si applicano a questa proprietà o alla procedura `Get` o `Set`. Vedere [elenco attributi](attribute-list.md).

- `Default`

  facoltativo. Specifica che questa proprietà è la proprietà predefinita della classe o della struttura in cui è definita. Le proprietà predefinite devono accettare parametri e possono essere impostate e recuperate senza specificare il nome della proprietà. Se si dichiara la proprietà come `Default`, non è possibile utilizzare `Private` sulla proprietà o su una delle relative routine di proprietà.

- `accessmodifier`

  Facoltativo nell'istruzione `Property` e al massimo una delle istruzioni `Get` e `Set`. Può essere uno dei seguenti:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  facoltativo. Può essere uno dei seguenti:

  - [Overload](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  facoltativo. Vedere [Shared](../modifiers/shared.md).

- `Shadows`

  facoltativo. Vedere [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  facoltativo. Vedere [ReadOnly](../modifiers/readonly.md).

- `WriteOnly`

  facoltativo. Vedere [WriteOnly](../modifiers/writeonly.md).

- `Iterator`

  facoltativo. Vedere [iteratore](../modifiers/iterator.md).

- `name`

  Obbligatorio. Nome della proprietà. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  facoltativo. Elenco di nomi di variabili locali che rappresentano i parametri di questa proprietà e possibili parametri aggiuntivi della procedura `Set`. Vedere [elenco di parametri](parameter-list.md).

- `returntype`

  Obbligatorio se `Option Strict` è `On`. Tipo di dati del valore restituito da questa proprietà.

- `Implements`

  facoltativo. Indica che questa proprietà implementa una o più proprietà, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa proprietà. Vedere [istruzione Implements](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle proprietà implementate.

  `implementedproperty [ , implementedproperty ... ]`

  Ogni `implementedproperty` presenta la sintassi e le parti seguenti:

  `interface.definedname`

  |Parte|Descrizione|
  |---|---|
  |`interface`|Obbligatorio. Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa proprietà.|
  |`definedname`|Obbligatorio. Nome con cui viene definita la proprietà in `interface`.|

- `Get`

  facoltativo. Obbligatorio se la proprietà è contrassegnata `ReadOnly`. Avvia una routine della proprietà `Get` utilizzata per restituire il valore della proprietà.  L'istruzione `Get` non viene utilizzata con le [proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  facoltativo. Blocco di istruzioni da eseguire all'interno della procedura `Get` o `Set`.

- `End Get`

  Termina la routine della proprietà `Get`.

- `Set`

  facoltativo. Obbligatorio se la proprietà è contrassegnata `WriteOnly`. Avvia una routine della proprietà `Set` utilizzata per archiviare il valore della proprietà.  L'istruzione `Set` non viene utilizzata con le [proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Termina la routine della proprietà `Set`.

- `End Property`

  Termina la definizione di questa proprietà.

## <a name="remarks"></a>Note

L'istruzione `Property` introduce la dichiarazione di una proprietà. Una proprietà può avere una routine `Get` (sola lettura), una procedura `Set` (sola scrittura) o entrambe (lettura/scrittura). È possibile omettere la procedura `Get` e `Set` quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

È possibile utilizzare `Property` solo a livello di classe. Ciò significa che il *contesto di dichiarazione* per una proprietà deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Per impostazione predefinita, le proprietà usano l'accesso pubblico. È possibile modificare il livello di accesso di una proprietà con un modificatore di accesso nell'istruzione `Property` ed è possibile modificare facoltativamente una delle routine di proprietà a un livello di accesso più restrittivo.

Visual Basic passa un parametro alla procedura `Set` durante le assegnazioni di proprietà. Se non si specifica un parametro per `Set`, il Integrated Development Environment (IDE) utilizza un parametro implicito denominato `value`. Questo parametro include il valore da assegnare alla proprietà. Questo valore viene in genere archiviato in una variabile locale privata e restituito ogni volta che viene chiamata la procedura `Get`.

## <a name="rules"></a>Regole

- **Livelli di accesso misti.** Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la procedura `Get` o `Set`, ma non per entrambi. In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà. Se, ad esempio, la proprietà è dichiarata `Friend`, è possibile dichiarare la procedura `Set` `Private`, ma non `Public`.

  Se si definisce una proprietà `ReadOnly` o `WriteOnly`, la routine della proprietà singola (rispettivamente `Get` o `Set`) rappresenta tutta la proprietà. Non è possibile dichiarare un livello di accesso diverso per una procedura di questo tipo, perché imposta due livelli di accesso per la proprietà.

- **Tipo restituito.** L'istruzione `Property` può dichiarare il tipo di dati del valore restituito. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.

  Se non si specifica `returntype`, la proprietà restituisce `Object`.

- **Implementazione.** Se questa proprietà Usa la parola chiave `Implements`, la classe o la struttura contenitore deve avere un'istruzione `Implements` immediatamente dopo la relativa istruzione `Class` o `Structure`. L'istruzione `Implements` deve includere ogni interfaccia specificata in `implementslist`. Tuttavia, il nome con cui un'interfaccia definisce il `Property` (in `definedname`) non deve corrispondere al nome di questa proprietà (in `name`).

## <a name="behavior"></a>Comportamento

- **Restituzione da una routine di proprietà.** Quando la procedura `Get` o `Set` restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che lo ha richiamato.

  Le istruzioni `Exit Property` e `Return` provocano una chiusura immediata da una routine Property. Qualsiasi numero di istruzioni `Exit Property` e `Return` può comparire in qualsiasi punto della procedura ed è possibile combinare le istruzioni `Exit Property` e `Return`.

- **Valore restituito.** Per restituire un valore da una routine `Get`, è possibile assegnare il valore al nome della proprietà o includerlo in un'istruzione `Return`. Nell'esempio seguente viene assegnato il valore restituito al nome della proprietà `quoteForTheDay`, quindi viene utilizzata l'istruzione `Exit Property` per restituire.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Se si usa `Exit Property` senza assegnare un valore a `name`, la procedura `Get` restituisce il valore predefinito per il tipo di dati della proprietà.

  L'istruzione `Return`, allo stesso tempo, assegna il valore restituito della procedura `Get` e chiude la procedura. Nell'esempio seguente viene illustrato questo.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarata una proprietà in una classe.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>Vedere anche

- [Proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
- [Istruzione Get](get-statement.md)
- [Istruzione Set](set-statement.md)
- [Elenco dei parametri](parameter-list.md)
- [Default](../modifiers/default.md)
