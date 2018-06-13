---
title: Istruzione Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: dbc48d14bac54809e4ddd12c87429bf407169950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604835"
---
# <a name="set-statement-visual-basic"></a>Istruzione Set (Visual Basic)
Dichiara un `Set` routine della proprietà utilizzata per assegnare un valore a una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Facoltativo per al massimo una del `Get` e `Set` istruzioni in questa proprietà. Può essere uno dei seguenti:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obbligatorio. Parametro contenente il nuovo valore per la proprietà.  
  
 `datatype`  
 Obbligatorio se `Option Strict` è `On`. Tipo di dati di `value` parametro. Tipo di dati specificato deve essere lo stesso come il tipo di dati della proprietà in cui questo `Set` istruzione viene dichiarata.  
  
 `statements`  
 Facoltativo. Uno o più istruzioni che vengono eseguite quando il `Set` viene chiamata una routine della proprietà.  
  
 `End Set`  
 Obbligatorio. Termina la definizione del `Set` routine della proprietà.  
  
## <a name="remarks"></a>Note  
 Ogni proprietà deve avere un `Set` routine della proprietà, a meno che la proprietà è contrassegnata come `ReadOnly`. Il `Set` procedure viene utilizzata per impostare il valore della proprietà.  
  
 Visual Basic chiama automaticamente una proprietà `Set` procedure quando un'istruzione di assegnazione fornisce un valore da archiviare nella proprietà.  
  
 Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà. Se non si specifica un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) usa un parametro implicito denominato `value`. Il parametro contiene il valore da assegnare alla proprietà. In genere archiviare il valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.  
  
 Il corpo della dichiarazione di proprietà può contenere solo della proprietà `Get` e `Set` procedure tra il [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md) e `End Property` istruzione. Non può contenere qualsiasi elemento diverso da tali procedure. In particolare, è possibile archiviare il valore della proprietà corrente. È necessario archiviare il valore di fuori della proprietà, perché se archiviata all'interno di una delle routine della proprietà, routine della proprietà non può accedere. In genere questo consiste nell'archiviare il valore in un [privata](../../../visual-basic/language-reference/modifiers/private.md) variabile dichiarata allo stesso livello della proprietà. È necessario definire un `Set` routine all'interno della proprietà a cui viene applicata.  
  
 Il `Set` procedure per impostazione predefinita il livello di accesso della proprietà che la contiene meno di utilizzare `accessmodifier` nel `Set` istruzione.  
  
## <a name="rules"></a>Regole  
  
-   **Livelli di accesso misti.** Se si definisce una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diverso per il `Get` o `Set` routine, ma non entrambi. In questo caso, il livello di accesso della routine deve essere più restrittivo a livello di accesso della proprietà. Ad esempio, se viene dichiarata la proprietà `Friend`, è possibile dichiarare il `Set` procedura `Private`, ma non `Public`.  
  
     Se si sta definendo un `WriteOnly` proprietà, il `Set` procedure rappresenta l'intera proprietà. Non è possibile dichiarare un accesso diverso livello per `Set`, poiché verrebbero specificati due livelli di accesso per la proprietà.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Restituzione da una routine di proprietà.** Quando il `Set` routine restituisce al codice chiamante, l'esecuzione continua dopo l'istruzione che ha fornito il valore da archiviare.  
  
     `Set` le routine della proprietà possono restituire utilizzando il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) o il [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà. Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Set` istruzione per impostare il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
