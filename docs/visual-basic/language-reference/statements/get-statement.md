---
title: Get (istruzione) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: ade54b2f00c540a1bf4ede311e1631b2c5d7e3ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742393"
---
# <a name="get-statement"></a>Istruzione Get
Dichiara un `Get` routine della proprietà utilizzata per recuperare il valore di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo in al massimo uno tra i `Get` e `Set` istruzioni in questa proprietà. Può essere uno dei seguenti:<br /><br /> -   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Facoltativo. Una o più istruzioni che vengono eseguite quando il `Get` routine della proprietà viene chiamato.|  
|`End Get`|Obbligatorio. Termina la definizione del `Get` routine della proprietà.|  
  
## <a name="remarks"></a>Note  
 Ogni proprietà deve avere una `Get` routine della proprietà, a meno che la proprietà è contrassegnata `WriteOnly`. Il `Get` procedure viene utilizzata per restituire il valore corrente della proprietà.  
  
 Visual Basic viene chiamata automaticamente una proprietà `Get` procedure quando un'espressione richiede il valore della proprietà.  
  
 Il corpo della dichiarazione di proprietà può contenere solo della proprietà `Get` e `Set` procedure tra il [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) e il `End Property` istruzione. Non può contenere qualsiasi elemento diverso da tali procedure. In particolare, è possibile archiviare il valore della proprietà corrente. È necessario archiviare questo valore di fuori della proprietà, poiché se si archivia, all'interno di una delle routine della proprietà, le altre routine di proprietà non è possibile accedervi. In genere questo consiste nell'archiviare il valore in una [privato](../../../visual-basic/language-reference/modifiers/private.md) variabile dichiarata allo stesso livello della proprietà. È necessario definire un `Get` procedure all'interno della proprietà a cui viene applicata.  
  
 Il `Get` predefinito usato dalla procedura a livello di accesso della proprietà che la contiene meno di utilizzare `accessmodifier` nel `Get` istruzione.  
  
## <a name="rules"></a>Regole  
  
-   **Livelli di accesso misti.** Se si sta definendo una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diversi per il `Get` o il `Set` procedure, ma non entrambi. In questo caso, il livello di accesso di routine deve essere più restrittivo rispetto a livello di accesso della proprietà. Ad esempio, se la proprietà è dichiarata `Friend`, è possibile dichiarare il `Get` routine `Private`, ma non `Public`.  
  
     Se si sta definendo un `ReadOnly` proprietà, il `Get` procedure rappresenta l'intera proprietà. Non è possibile dichiarare un accesso diverso a livello di `Get`, poiché verrebbero specificati due livelli di accesso per la proprietà.  
  
-   **Tipo restituito.** Il [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) può dichiarare il tipo di dati del valore restituito. Il `Get` routine restituisce automaticamente che tipo di dati. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
     Se il `Property` istruzione non è specificato `returntype`, la stored procedure restituisce `Object`.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Restituzione da una procedura.** Quando il `Get` routine restituisce al codice chiamante, l'esecuzione continua all'interno dell'istruzione che ha richiesto il valore della proprietà.  
  
     `Get` le routine della proprietà possono restituire un valore usando il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) o assegnando il valore restituito per il nome della proprietà. Per altre informazioni, vedere "Valore di restituire" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà. Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.  
  
-   **Valore restituito.** Per restituire un valore da un `Get` procedure, è possibile assegnare il valore per il nome della proprietà o includerlo in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md). Il `Return` istruzione assegna contemporaneamente il `Get` procedure restituire valore e viene chiuso la procedura.  
  
     Se si usa `Exit Property` senza assegnarle un valore per il nome della proprietà di `Get` procedure restituisce il valore predefinito per il tipo di dati della proprietà. Per altre informazioni, vedere "Valore di restituire" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     L'esempio seguente illustra due modi la proprietà di sola lettura `quoteForTheDay` può restituire il valore della variabile privata `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Get` istruzione per restituire il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Procedura dettagliata: Definizione delle classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
