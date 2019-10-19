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
ms.openlocfilehash: cb0dc76d110f3e6a3ea3e74cc0bfb5a669b35396
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583230"
---
# <a name="set-statement-visual-basic"></a>Istruzione Set (Visual Basic)
Dichiara una routine della proprietà `Set` utilizzata per assegnare un valore a una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Parametro facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Facoltativo al massimo una delle istruzioni `Get` e `Set` in questa proprietà. Può essere uno dei seguenti:  
  
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obbligatorio. Parametro che contiene il nuovo valore per la proprietà.  
  
 `datatype`  
 Obbligatorio se `Option Strict` è `On`. Tipo di dati del parametro `value`. Il tipo di dati specificato deve corrispondere al tipo di dati della proprietà in cui è dichiarata questa istruzione `Set`.  
  
 `statements`  
 Parametro facoltativo. Una o più istruzioni eseguite quando viene chiamata la routine della proprietà `Set`.  
  
 `End Set`  
 Obbligatorio. Termina la definizione della routine della proprietà `Set`.  
  
## <a name="remarks"></a>Note  
 Ogni proprietà deve disporre di una routine della proprietà `Set`, a meno che la proprietà non sia contrassegnata `ReadOnly`. La procedura `Set` viene utilizzata per impostare il valore della proprietà.  
  
 Visual Basic chiama automaticamente una routine `Set` della proprietà quando un'istruzione di assegnazione fornisce un valore da archiviare nella proprietà.  
  
 Visual Basic passa un parametro alla routine `Set` durante le assegnazioni di proprietà. Se non si specifica un parametro per `Set`, l'Integrated Development Environment (IDE) utilizza un parametro implicito denominato `value`. Il parametro include il valore da assegnare alla proprietà. Questo valore viene in genere archiviato in una variabile locale privata e restituito ogni volta che viene chiamata la procedura `Get`.  
  
 Il corpo della dichiarazione di proprietà può contenere solo le `Get` della proprietà e `Set` le routine tra l' [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`. Non è possibile archiviare un valore diverso da tali procedure. In particolare, non è possibile archiviare il valore corrente della proprietà. È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi. L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../../../visual-basic/language-reference/modifiers/private.md) dichiarata allo stesso livello della proprietà. È necessario definire una procedura di `Set` all'interno della proprietà a cui si applica.  
  
 Per impostazione predefinita, la procedura `Set` il livello di accesso della proprietà che lo contiene, a meno che non si usi `accessmodifier` nell'istruzione `Set`.  
  
## <a name="rules"></a>Regole  
  
- **Livelli di accesso misti.** Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la procedura `Get` o per la `Set`, ma non per entrambi. In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà. Se, ad esempio, la proprietà viene dichiarata `Friend`, è possibile dichiarare la routine `Set` `Private`, ma non `Public`.  
  
     Se si definisce una proprietà `WriteOnly`, la routine `Set` rappresenta l'intera proprietà. Non è possibile dichiarare un livello di accesso diverso per `Set`, perché in questo modo verrebbero impostati due livelli di accesso per la proprietà.  
  
## <a name="behavior"></a>Comportamento  
  
- **Restituzione da una routine di proprietà.** Quando la `Set` procedura restituisce al codice chiamante, l'esecuzione continua seguendo l'istruzione che ha fornito il valore da archiviare.  
  
     `Set` le routine della proprietà possono restituire utilizzando l'istruzione [return](../../../visual-basic/language-reference/statements/return-statement.md) o l' [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Le istruzioni `Exit Property` e `Return` generano un'uscita immediata da una routine Property. Un numero qualsiasi di istruzioni `Exit Property` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Property` e `Return` istruzioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Set` per impostare il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
