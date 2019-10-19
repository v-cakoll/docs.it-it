---
title: Istruzione Get (Visual Basic)
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
ms.openlocfilehash: d76155b8ff29e4f5e9206ae8fc689fa4fcaf3b8c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581826"
---
# <a name="get-statement"></a>Istruzione Get
Dichiara una routine della proprietà `Get` utilizzata per recuperare il valore di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Parametro facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo al massimo una delle istruzioni `Get` e `Set` in questa proprietà. Può essere uno dei seguenti:<br /><br /> -   [protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privato](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Parametro facoltativo. Una o più istruzioni eseguite quando viene chiamata la routine della proprietà `Get`.|  
|`End Get`|Obbligatorio. Termina la definizione della routine della proprietà `Get`.|  
  
## <a name="remarks"></a>Note  
 Ogni proprietà deve disporre di una routine della proprietà `Get`, a meno che la proprietà non sia contrassegnata `WriteOnly`. La procedura `Get` viene utilizzata per restituire il valore corrente della proprietà.  
  
 Visual Basic chiama automaticamente una routine `Get` della proprietà quando un'espressione richiede il valore della proprietà.  
  
 Il corpo della dichiarazione di proprietà può contenere solo le `Get` della proprietà e `Set` le routine tra l' [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`. Non è possibile archiviare un valore diverso da tali procedure. In particolare, non è possibile archiviare il valore corrente della proprietà. È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi. L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../../../visual-basic/language-reference/modifiers/private.md) dichiarata allo stesso livello della proprietà. È necessario definire una procedura di `Get` all'interno della proprietà a cui si applica.  
  
 Per impostazione predefinita, la procedura `Get` il livello di accesso della proprietà che lo contiene, a meno che non si usi `accessmodifier` nell'istruzione `Get`.  
  
## <a name="rules"></a>Regole  
  
- **Livelli di accesso misti.** Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la procedura `Get` o per la `Set`, ma non per entrambi. In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà. Se, ad esempio, la proprietà viene dichiarata `Friend`, è possibile dichiarare la routine `Get` `Private`, ma non `Public`.  
  
     Se si definisce una proprietà `ReadOnly`, la routine `Get` rappresenta l'intera proprietà. Non è possibile dichiarare un livello di accesso diverso per `Get`, perché in questo modo verrebbero impostati due livelli di accesso per la proprietà.  
  
- **Tipo restituito.** L' [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md) può dichiarare il tipo di dati del valore restituito. La procedura `Get` restituisce automaticamente il tipo di dati. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.  
  
     Se l'istruzione `Property` non specifica `returntype`, la procedura restituisce `Object`.  
  
## <a name="behavior"></a>Comportamento  
  
- **Restituzione da una routine.** Quando la `Get` procedura restituisce al codice chiamante, l'esecuzione continua all'interno dell'istruzione che ha richiesto il valore della proprietà.  
  
     `Get` routine Property può restituire un valore utilizzando l' [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md) o assegnando il valore restituito al nome della proprietà. Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Le istruzioni `Exit Property` e `Return` generano un'uscita immediata da una routine Property. Un numero qualsiasi di istruzioni `Exit Property` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Property` e `Return` istruzioni.  
  
- **Valore restituito.** Per restituire un valore da una routine di `Get`, è possibile assegnare il valore al nome della proprietà o includerlo in un' [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md). L'istruzione `Return` assegna simultaneamente il valore restituito della routine `Get` e chiude la procedura.  
  
     Se si utilizza `Exit Property` senza assegnare un valore al nome della proprietà, la routine `Get` restituisce il valore predefinito per il tipo di dati della proprietà. Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Nell'esempio seguente vengono illustrati due modi per la proprietà di sola lettura `quoteForTheDay` possibile restituire il valore contenuto nella variabile privata `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Get` per restituire il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Procedura dettagliata: Definizione delle classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
