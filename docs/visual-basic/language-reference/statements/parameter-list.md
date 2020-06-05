---
title: Elenco parametri
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404317"
---
# <a name="parameter-list-visual-basic"></a>Elenco dei parametri (Visual Basic)

Specifica i parametri che una routine prevede quando viene chiamata. Più parametri sono separati da virgole. Di seguito è riportata la sintassi per un parametro.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Parti

`attributelist`  
Facoltativa. Elenco degli attributi che si applicano a questo parametro. È necessario racchiudere l' [elenco degli attributi](attribute-list.md) tra parentesi angolari (" `<` " e " `>` ").

`Optional`  
Facoltativa. Specifica che questo parametro non è obbligatorio quando viene chiamata la stored procedure.

`ByVal`  
Facoltativa. Specifica che la routine non può sostituire o riassegnare l'elemento della variabile sottostante all'argomento corrispondente nel codice chiamante.

`ByRef`  
Facoltativa. Specifica che la stored procedure può modificare l'elemento della variabile sottostante nel codice chiamante nello stesso modo in cui è possibile il codice chiamante.

`ParamArray`  
Facoltativa. Specifica che l'ultimo parametro nell'elenco di parametri è una matrice facoltativa di elementi del tipo di dati specificato. Ciò consente al codice chiamante di passare un numero arbitrario di argomenti alla procedura.

`parametername`  
Obbligatorio. Nome della variabile locale che rappresenta il parametro.

`parametertype`  
Obbligatorio se `Option Strict` è `On` . Tipo di dati della variabile locale che rappresenta il parametro.

`defaultvalue`  
Obbligatorio per i `Optional` parametri. Qualsiasi costante o espressione costante che restituisce il tipo di dati del parametro. Se il tipo è `Object` o una classe, un'interfaccia, una matrice o una struttura, il valore predefinito può essere solo `Nothing` .

## <a name="remarks"></a>Commenti

I parametri sono racchiusi tra parentesi e separati da virgole. Un parametro può essere dichiarato con qualsiasi tipo di dati. Se non si specifica `parametertype` , il valore predefinito è `Object` .

Quando il codice chiamante chiama la stored procedure, passa un *argomento* a ogni parametro obbligatorio. Per ulteriori informazioni, vedere [differenze tra parametri e argomenti](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

L'argomento che il codice chiamante passa a ogni parametro è un puntatore a un elemento sottostante nel codice chiamante. Se questo elemento non è *variabile* (costante, valore letterale, enumerazione o espressione), non è possibile modificare il codice. Se è un elemento *variabile* (una variabile dichiarata, un campo, una proprietà, un elemento di matrice o un elemento della struttura), il codice chiamante può modificarlo. Per ulteriori informazioni, vedere [differenze tra argomenti modificabili e non modificabili](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Se viene passato un elemento variabile `ByRef` , può essere modificato anche dalla procedura. Per ulteriori informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Regole

- **Parentesi.** Se si specifica un elenco di parametri, è necessario racchiuderlo tra parentesi. Se non sono presenti parametri, è comunque possibile usare le parentesi che racchiudono un elenco vuoto. Ciò migliora la leggibilità del codice chiarendo che l'elemento è una routine.

- **Parametri facoltativi.** Se si usa il `Optional` modificatore su un parametro, anche tutti i parametri successivi nell'elenco devono essere facoltativi e devono essere dichiarati usando il `Optional` modificatore.

     Ogni dichiarazione di parametro facoltativa deve fornire la `defaultvalue` clausola.

     Per ulteriori informazioni, vedere [parametri facoltativi](../../programming-guide/language-features/procedures/optional-parameters.md).

- **Matrici di parametri.** È necessario specificare `ByVal` per un `ParamArray` parametro.

     Non è possibile utilizzare sia `Optional` che `ParamArray` nello stesso elenco di parametri.

     Per altre informazioni, vedere [matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md).

- **Passaggio del meccanismo.** Il meccanismo predefinito per ogni argomento è `ByVal` , il che significa che la procedura non può modificare l'elemento della variabile sottostante. Tuttavia, se l'elemento è un tipo di riferimento, la procedura può modificare il contenuto o i membri dell'oggetto sottostante, anche se non è in grado di sostituire o riassegnare l'oggetto stesso.

- **Nomi dei parametri.** Se il tipo di dati del parametro è una matrice, seguire `parametername` immediatamente le parentesi. Per ulteriori informazioni sui nomi dei parametri, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una `Function` procedura che definisce due parametri.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Istruzione Function](function-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Istruzione Structure](structure-statement.md)
- [Option Strict Statement](option-strict-statement.md)
- [Panoramica degli attributi](../../programming-guide/concepts/attributes/index.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
