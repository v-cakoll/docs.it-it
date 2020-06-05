---
title: Routine Property
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
ms.openlocfilehash: cb5b0e12512e476b7c96bbfb19f8e4f470f6b498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363733"
---
# <a name="property-procedures-visual-basic"></a>Routine Property (Visual Basic)

Una routine di proprietà è una serie di istruzioni Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, una classe o una struttura. Le routine di proprietà sono note anche come *funzioni di accesso alle proprietà*.

Visual Basic fornisce le routine di proprietà seguenti:

- Una `Get` routine restituisce il valore di una proprietà. Viene chiamato quando si accede alla proprietà in un'espressione.
- Una `Set` routine imposta una proprietà su un valore, incluso un riferimento a un oggetto. Viene chiamato quando si assegna un valore alla proprietà.

In genere, le routine di proprietà vengono definite in coppie utilizzando le `Get` `Set` istruzioni e, ma è possibile definire una sola routine solo se la proprietà è di sola lettura ([istruzione Get](../../../language-reference/statements/get-statement.md)) o di sola scrittura ([istruzione set](../../../language-reference/statements/set-statement.md)).

È possibile omettere `Get` la `Set` procedura e quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).

È possibile definire le proprietà in classi, strutture e moduli. `Public`Per impostazione predefinita, le proprietà sono, quindi è possibile chiamarle da qualsiasi punto dell'applicazione in grado di accedere al contenitore della proprietà.

Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](differences-between-properties-and-variables.md).

## <a name="declaration-syntax"></a>Sintassi di dichiarazione

Una proprietà viene definita da un blocco di codice racchiuso tra l' [istruzione Property](../../../language-reference/statements/property-statement.md) e l' `End Property` istruzione. All'interno di questo blocco, ogni routine di proprietà viene visualizzata come un blocco interno racchiuso tra un'istruzione di dichiarazione ( `Get` o `Set` ) e la `End` dichiarazione corrispondente.

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

`Modifiers`Può specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e allo shadowing, nonché se la proprietà è di sola lettura o di sola scrittura. L'oggetto `AccessLevel` nella `Get` `Set` routine o può essere qualsiasi livello più restrittivo del livello di accesso specificato per la proprietà stessa. Per ulteriori informazioni, vedere [istruzione Property](../../../language-reference/statements/property-statement.md).

### <a name="data-type"></a>Tipo di dati

Il tipo di dati e il livello di accesso dell'entità di una proprietà sono definiti nell' `Property` istruzione, non nelle routine della proprietà. Una proprietà può avere un solo tipo di dati. Non è ad esempio possibile definire una proprietà per archiviare un `Decimal` valore, ma recuperare un `Double` valore.

### <a name="access-level"></a>Livello di accesso

Tuttavia, è possibile definire un livello di accesso principale per una proprietà e limitare ulteriormente il livello di accesso in una delle relative routine di proprietà. Ad esempio, è possibile definire una `Public` proprietà e quindi definire una `Private Set` routine. La `Get` procedura rimane `Public` . È possibile modificare il livello di accesso solo in una delle routine di una proprietà ed è possibile renderlo solo più restrittivo del livello di accesso principale. Per altre informazioni, vedere [procedura: dichiarare una proprietà con livelli di accesso misti](how-to-declare-a-property-with-mixed-access-levels.md).

## <a name="parameter-declaration"></a>Dichiarazione di parametro

Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](sub-procedures.md), con la differenza che il meccanismo di passaggio deve essere `ByVal` .

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

In una `Set` routine, il nuovo valore della proprietà viene passato al parametro dell' `Set` istruzione. Se si dichiara in modo esplicito un parametro, è necessario dichiararlo con lo stesso tipo di dati della proprietà. Se non si dichiara un parametro, il compilatore usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.

## <a name="calling-syntax"></a>Sintassi di chiamata

Per richiamare una routine di proprietà in modo implicito, è necessario fare riferimento alla proprietà. Usare il nome della proprietà nello stesso modo in cui si usa il nome di una variabile, ad eccezione del fatto che è necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi. Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.

La sintassi per una chiamata implicita a una `Set` procedura è la seguente:

```vb
propertyname[(argumentlist)] = expression
```

La sintassi per una chiamata implicita a una `Get` procedura è la seguente:

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata

Nella proprietà seguente viene archiviato un nome completo come due nomi costitutivi, il primo nome e il cognome. Quando il codice chiamante viene letto `fullName` , la `Get` procedura combina i due nomi costitutivi e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, la `Set` routine tenta di suddividerla in due nomi costitutivi. Se non trova uno spazio, lo archivia come nome.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine di proprietà di `fullName` :

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>Vedere anche

- [Procedure](index.md)
- [Routine Function](function-procedures.md)
- [Routine di operatore](operator-procedures.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](differences-between-properties-and-variables.md)
- [Procedura: creare una proprietà](how-to-create-a-property.md)
- [Procedura: chiamare una routine di proprietà](how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](how-to-get-a-value-from-a-property.md)
