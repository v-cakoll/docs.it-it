---
title: Elenco dei parametri (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c7190b618aa98c91b826ca7c065660d3b19c31a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-list-visual-basic"></a>Elenco dei parametri (Visual Basic)
Specifica i parametri di che una procedura prevista quando viene chiamato. Più parametri sono separati da virgole. Di seguito è la sintassi per un parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Parametro facoltativo. Elenco di attributi che si applicano a questo parametro. È necessario racchiudere il [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi quadre ("`<`"e"`>`").  
  
 `Optional`  
 Parametro facoltativo. Specifica che questo parametro non è obbligatorio quando viene chiamata la procedura.  
  
 `ByVal`  
 Parametro facoltativo. Specifica che la routine non è possibile sostituire o riassegnare l'elemento variabile sottostante all'argomento corrispondente nel codice chiamante.  
  
 `ByRef`  
 Parametro facoltativo. Specifica che la routine può modificare l'elemento variabile sottostante nel codice chiamante allo stesso modo che il codice.  
  
 `ParamArray`  
 Parametro facoltativo. Specifica che l'ultimo parametro nell'elenco di parametri è una matrice facoltativa di elementi del tipo di dati specificato. In questo modo il codice chiamante può passare un numero arbitrario di argomenti per la procedura.  
  
 `parametername`  
 Obbligatorio. Nome della variabile locale che rappresenta il parametro.  
  
 `parametertype`  
 Obbligatorio se `Option Strict` è `On`. Tipo di dati della variabile locale che rappresenta il parametro.  
  
 `defaultvalue`  
 Necessario per `Optional` parametri. Qualsiasi espressione di costante o una costante che restituisce il tipo di dati del parametro. Se il tipo è `Object`, o una classe, interfaccia, una matrice o una struttura, il valore predefinito può essere solo `Nothing`.  
  
## <a name="remarks"></a>Note  
 I parametri sono racchiusi tra parentesi e separati da virgole. Un parametro può essere dichiarato con qualsiasi tipo di dati. Se non si specifica `parametertype`, il valore predefinito è `Object`.  
  
 Quando il codice chiamante chiama la routine, passa un *argomento* a ogni parametro obbligatorio. Per ulteriori informazioni, vedere [le differenze tra parametri e argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 L'argomento, che il codice chiamante viene passata a ogni parametro è un puntatore a un elemento sottostante nel codice chiamante. Se questo elemento è *variabile* (una costante, valore letterale, enumerazione o espressione), non è possibile ottenere il codice per modificarlo. Se si tratta di un *variabile* elemento (una variabile dichiarata, campi, proprietà, elemento di matrice o elemento di struttura), il codice chiamante può modificarlo. Per ulteriori informazioni, vedere [le differenze tra modificabile e non è modificabile argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Se viene passato un elemento variabile `ByRef`, la routine può modificare anche. Per ulteriori informazioni, vedere [le differenze tra il passaggio di un argomento per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Regole  
  
-   **Parentesi.** Se si specifica un elenco di parametri, è necessario racchiuderlo tra parentesi. Se non sono presenti parametri, è comunque possibile usare parentesi che racchiudono un elenco vuoto. Per migliorare la leggibilità del codice per chiarire che l'elemento è una stored procedure.  
  
-   **Parametri facoltativi.** Se si utilizza il `Optional` modificatore su un parametro, tutti i parametri successivi nell'elenco deve essere facoltativi ed essere dichiarati mediante il `Optional` modificatore.  
  
     Ogni dichiarazione di parametro facoltativo è necessario fornire il `defaultvalue` clausola.  
  
     Per ulteriori informazioni, vedere [parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Matrici di parametri.** È necessario specificare `ByVal` per un `ParamArray` parametro.  
  
     È possibile utilizzare sia `Optional` e `ParamArray` nello stesso elenco di parametri.  
  
     Per ulteriori informazioni, vedere [matrici di parametro](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Meccanismo di passaggio.** Il meccanismo predefinito per ogni argomento è `ByVal`, ovvero la procedura non può modificare l'elemento variabile sottostante. Tuttavia, se l'elemento è un tipo riferimento, la routine può modificare il contenuto o i membri dell'oggetto sottostante, anche se non può sostituire o riassegnare l'oggetto stesso.  
  
-   **Nomi dei parametri.** Se il tipo di dati del parametro è una matrice, seguire `parametername` parentesi immediatamente. Per ulteriori informazioni sui nomi dei parametri, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un `Function` routine che definisce due parametri.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
