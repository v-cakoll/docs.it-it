---
title: Routine Property (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 118c9e776813f303ed921946f4cf6f1236ac02e3
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040967"
---
# <a name="property-procedures-visual-basic"></a>Routine Property (Visual Basic)

Una routine di proprietà è una serie di istruzioni Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, una classe o una struttura. Le routine di proprietà sono note anche come *funzioni di accesso alle proprietà*.

Visual Basic fornisce le routine di proprietà seguenti:

- Una routine `Get` restituisce il valore di una proprietà. Viene chiamato quando si accede alla proprietà in un'espressione.
- Una routine `Set` imposta una proprietà su un valore, incluso un riferimento a un oggetto. Viene chiamato quando si assegna un valore alla proprietà.

In genere, le routine di proprietà vengono definite in coppie, usando le istruzioni `Get` e `Set`, ma è possibile definire una sola procedura solo se la proprietà è di sola lettura ([istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o di sola scrittura ([istruzione set](../../../../visual-basic/language-reference/statements/set-statement.md)).

Quando si usa una proprietà implementata automaticamente, è possibile omettere il `Get` e `Set` procedura. Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).

È possibile definire le proprietà in classi, strutture e moduli. Per impostazione predefinita, le proprietà sono `Public`, quindi è possibile chiamarle da qualsiasi punto dell'applicazione in grado di accedere al contenitore della proprietà.

Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](differences-between-properties-and-variables.md).

## <a name="declaration-syntax"></a>Sintassi di dichiarazione

Una proprietà viene definita da un blocco di codice racchiuso tra l' [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`. All'interno di questo blocco ogni routine di proprietà viene visualizzata come un blocco interno racchiuso tra un'istruzione di dichiarazione (`Get` o `Set`) e la dichiarazione `End` corrispondente.

La sintassi per la dichiarazione di una proprietà e delle relative procedure è la seguente:

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

Il `Modifiers` può specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e allo shadowing, nonché se la proprietà è di sola lettura o di sola scrittura. Il `AccessLevel` della procedura `Get` o `Set` può essere qualsiasi livello più restrittivo del livello di accesso specificato per la proprietà stessa. Per ulteriori informazioni, vedere [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md).

### <a name="data-type"></a>Tipo di dati

Il tipo di dati e il livello di accesso dell'entità di una proprietà sono definiti nell'istruzione `Property`, non nelle routine della proprietà. Una proprietà può avere un solo tipo di dati. Non è ad esempio possibile definire una proprietà per archiviare un valore di `Decimal` ma recuperare un valore `Double`.

### <a name="access-level"></a>Livello di accesso

Tuttavia, è possibile definire un livello di accesso principale per una proprietà e limitare ulteriormente il livello di accesso in una delle relative routine di proprietà. Ad esempio, è possibile definire una proprietà `Public` e quindi definire una `Private Set` routine. La `Get` routine rimane `Public`. È possibile modificare il livello di accesso solo in una delle routine di una proprietà ed è possibile renderlo solo più restrittivo del livello di accesso principale. Per altre informazioni, vedere [procedura: dichiarare una proprietà con livelli di accesso misti](how-to-declare-a-property-with-mixed-access-levels.md).

## <a name="parameter-declaration"></a>Dichiarazione di parametro

Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](sub-procedures.md), con la differenza che il meccanismo di passaggio deve essere `ByVal`.

La sintassi per ogni parametro nell'elenco di parametri è la seguente:

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è la seguente:

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a>Valore proprietà

In una `Get` routine, il valore restituito viene fornito all'espressione chiamante come valore della proprietà.

In una procedura `Set` il nuovo valore della proprietà viene passato al parametro dell'istruzione `Set`. Se si dichiara in modo esplicito un parametro, è necessario dichiararlo con lo stesso tipo di dati della proprietà. Se non si dichiara un parametro, il compilatore usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.

## <a name="calling-syntax"></a>Sintassi di chiamata

Per richiamare una routine di proprietà in modo implicito, è necessario fare riferimento alla proprietà. Usare il nome della proprietà nello stesso modo in cui si usa il nome di una variabile, ad eccezione del fatto che è necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi. Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.

La sintassi per una chiamata implicita a una procedura `Set` è la seguente:

```vb
propertyname[(argumentlist)] = expression
```

La sintassi per una chiamata implicita a una procedura `Get` è la seguente:

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata

Nella proprietà seguente viene archiviato un nome completo come due nomi costitutivi, il primo nome e il cognome. Quando il codice chiamante legge `fullName`, la procedura `Get` combina i due nomi costitutivi e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, la `Set` routine tenta di suddividerla in due nomi costitutivi. Se non trova uno spazio, lo archivia come nome.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine di proprietà di `fullName`:

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>Vedere anche

- [Routine](index.md)
- [Routine Function](function-procedures.md)
- [Routine di operatore](operator-procedures.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](how-to-create-a-property.md)
- [Procedura: Chiamare una routine di proprietà](how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](how-to-get-a-value-from-a-property.md)
