---
title: Elenco dei parametri (Visual Basic)
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
ms.openlocfilehash: 651f08812032aa1c5aacc04fdb3d7f491f12b607
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836285"
---
# <a name="parameter-list-visual-basic"></a>Elenco dei parametri (Visual Basic)
Specifica i parametri di che una routine prevede il quando viene chiamato. Più parametri sono separati da virgole. Di seguito è la sintassi per un parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativo. Elenco di attributi da applicare a questo parametro. È necessario racchiudere il [elenco di attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").  
  
 `Optional`  
 Facoltativo. Specifica che questo parametro non è necessario quando viene chiamata la procedura.  
  
 `ByVal`  
 Facoltativo. Specifica che la procedura non è possibile sostituire o riassegnare l'elemento variabile sottostante all'argomento corrispondente nel codice chiamante.  
  
 `ByRef`  
 Facoltativo. Specifica che la routine può modificare l'elemento variabile sottostante nel codice chiamante allo stesso modo che il codice chiama può.  
  
 `ParamArray`  
 Facoltativo. Specifica che l'ultimo parametro nell'elenco dei parametri è una matrice facoltativa di elementi del tipo di dati specificato. In questo modo il codice chiamante può passare un numero arbitrario di argomenti per la procedura.  
  
 `parametername`  
 Obbligatorio. Nome della variabile locale che rappresenta il parametro.  
  
 `parametertype`  
 Obbligatorio se `Option Strict` è `On`. Tipo di dati della variabile locale che rappresenta il parametro.  
  
 `defaultvalue`  
 Obbligatorio per `Optional` parametri. Qualsiasi costante o espressione costante che restituisce il tipo di dati del parametro. Se il tipo è `Object`, o una classe, interfaccia, una matrice o una struttura, il valore predefinito può essere solo `Nothing`.  
  
## <a name="remarks"></a>Note  
 I parametri sono racchiusi tra parentesi e separati da virgole. Un parametro può essere dichiarato con qualsiasi tipo di dati. Se non si specifica `parametertype`, per impostazione predefinita `Object`.  
  
 Quando il codice chiamante chiama la routine, passa un' *argomento* per ogni parametro obbligatorio. Per altre informazioni, vedere [differenze tra parametri e argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 L'argomento che nel codice chiama vengono passati a ogni parametro è un puntatore a un elemento sottostante nel codice chiamante. Se questo elemento è *variabile* (una costante, valore letterale, enumerazione o espressione), è Impossibile per il codice per modificarlo. Se si tratta di un *variabile* elemento (una variabile dichiarata, campo, proprietà, elemento di matrice o elemento di struttura), il codice chiamante può modificarlo. Per altre informazioni, vedere [differenze tra modificabile e non è modificabile argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Se viene passato un elemento variable `ByRef`, cambia anche la procedura. Per altre informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Regole  
  
-   **Parentesi.** Se si specifica un elenco di parametri, è necessario racchiuderlo tra parentesi. Se non sono presenti parametri, è comunque possibile usare parentesi che racchiudono un elenco vuoto. Ciò migliora la leggibilità del codice per chiarire che l'elemento è una procedura.  
  
-   **Parametri facoltativi.** Se si usa la `Optional` modificatore in un parametro, tutti i parametri successivi nell'elenco devono anche essere facoltativi ed essere dichiarati utilizzando la `Optional` modificatore.  
  
     Ogni dichiarazione di parametro facoltativo deve fornire il `defaultvalue` clausola.  
  
     Per altre informazioni, vedere [parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Matrici di parametri.** È necessario specificare `ByVal` per un `ParamArray` parametro.  
  
     Non è possibile usare entrambe `Optional` e `ParamArray` nell'elenco dei parametri stessi.  
  
     Per altre informazioni, vedere [matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Meccanismo di passaggio.** Il meccanismo predefinito per ogni argomento è `ByVal`, che significa che la procedura non è possibile modificare l'elemento variabile sottostante. Tuttavia, se l'elemento è un tipo riferimento, la routine può modificare il contenuto o i membri dell'oggetto sottostante, anche se non può sostituire o riassegnare l'oggetto stesso.  
  
-   **Nomi dei parametri.** Se il tipo di dati del parametro è una matrice, seguire `parametername` immediatamente racchiusi tra parentesi. Per altre informazioni sui nomi dei parametri, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un `Function` procedure che definisce due parametri.  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
