---
title: Istruzione Set
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
ms.openlocfilehash: 49d4c36805b64d7232a94e818256723a0437b6ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404187"
---
# <a name="set-statement-visual-basic"></a>Istruzione Set (Visual Basic)
Dichiara una `Set` routine della proprietà usata per assegnare un valore a una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativa. Vedere [elenco attributi](attribute-list.md).  
  
 `accessmodifier`  
 Facoltativo al massimo una delle `Get` `Set` istruzioni e in questa proprietà. Può essere uno dei seguenti:  
  
- [Protetto](../modifiers/protected.md)  
  
- [Amico](../modifiers/friend.md)  
  
- [Privata](../modifiers/private.md)  
  
- `Protected Friend`  
  
 Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obbligatorio. Parametro che contiene il nuovo valore per la proprietà.  
  
 `datatype`  
 Obbligatorio se `Option Strict` è `On` . Tipo di dati del `value` parametro. Il tipo di dati specificato deve corrispondere al tipo di dati della proprietà in cui `Set` è dichiarata questa istruzione.  
  
 `statements`  
 Facoltativa. Una o più istruzioni che vengono eseguite quando `Set` viene chiamata la routine della proprietà.  
  
 `End Set`  
 Obbligatorio. Termina la definizione della routine della `Set` Proprietà.  
  
## <a name="remarks"></a>Commenti  
 Ogni proprietà deve disporre di una `Set` routine Property, a meno che la proprietà non sia contrassegnata come `ReadOnly` . La `Set` procedura viene utilizzata per impostare il valore della proprietà.  
  
 Visual Basic chiama automaticamente la routine di una proprietà `Set` quando un'istruzione di assegnazione fornisce un valore da archiviare nella proprietà.  
  
 Visual Basic passa un parametro alla `Set` routine durante le assegnazioni di proprietà. Se non si specifica un parametro per `Set` , il Integrated Development Environment (IDE) utilizza un parametro implicito denominato `value` . Il parametro include il valore da assegnare alla proprietà. Questo valore viene in genere archiviato in una variabile locale privata e restituito ogni volta che `Get` viene chiamata la stored procedure.  
  
 Il corpo della dichiarazione di proprietà può contenere solo le `Get` routine e della proprietà `Set` tra l' [istruzione Property](property-statement.md) e l' `End Property` istruzione. Non è possibile archiviare un valore diverso da tali procedure. In particolare, non è possibile archiviare il valore corrente della proprietà. È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi. L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../modifiers/private.md) dichiarata allo stesso livello della proprietà. È necessario definire una `Set` routine all'interno della proprietà a cui si applica.  
  
 `Set`Per impostazione predefinita, la procedura viene impostata sul livello di accesso della proprietà che lo contiene, a meno che non si utilizzi `accessmodifier` nell' `Set` istruzione.  
  
## <a name="rules"></a>Regole  
  
- **Livelli di accesso misti.** Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la `Get` routine o `Set` , ma non per entrambi. In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà. Se, ad esempio, la proprietà è dichiarata `Friend` , è possibile dichiarare la `Set` routine `Private` , ma non `Public` .  
  
     Se si definisce una `WriteOnly` proprietà, la `Set` routine rappresenta l'intera proprietà. Non è possibile dichiarare un livello di accesso diverso per `Set` , perché in questo caso verrebbero impostati due livelli di accesso per la proprietà.  
  
## <a name="behavior"></a>Comportamento  
  
- **Restituzione da una routine di proprietà.** Quando la `Set` procedura viene restituita al codice chiamante, l'esecuzione continua seguendo l'istruzione che ha fornito il valore da archiviare.  
  
     `Set`le routine di proprietà possono restituire utilizzando l'istruzione [return](return-statement.md) o l' [istruzione Exit](exit-statement.md).  
  
     Le `Exit Property` `Return` istruzioni e generano un'uscita immediata da una routine di proprietà. Qualsiasi numero di `Exit Property` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Property` `Return` istruzioni e.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Set` istruzione per impostare il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Get](get-statement.md)
- [Property Statement](property-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Routine Property](../../programming-guide/language-features/procedures/property-procedures.md)
