---
title: Istruzione Get
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
ms.openlocfilehash: 31936fb2c8f658203a43702a2b5fa4ee2481beb5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404602"
---
# <a name="get-statement"></a>Istruzione Get
Dichiara una `Get` routine di proprietà utilizzata per recuperare il valore di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Facoltativa. Vedere [elenco attributi](attribute-list.md).|  
|`accessmodifier`|Facoltativo al massimo una delle `Get` `Set` istruzioni e in questa proprietà. Può essere uno dei seguenti:<br /><br /> -   [Protetto](../modifiers/protected.md)<br />-   [Amico](../modifiers/friend.md)<br />-   [Privata](../modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Facoltativa. Una o più istruzioni che vengono eseguite quando `Get` viene chiamata la routine della proprietà.|  
|`End Get`|Obbligatorio. Termina la definizione della routine della `Get` Proprietà.|  
  
## <a name="remarks"></a>Commenti  
 Ogni proprietà deve disporre di una `Get` routine Property, a meno che la proprietà non sia contrassegnata come `WriteOnly` . La `Get` stored procedure viene utilizzata per restituire il valore corrente della proprietà.  
  
 Visual Basic chiama automaticamente la routine di una proprietà `Get` quando un'espressione richiede il valore della proprietà.  
  
 Il corpo della dichiarazione di proprietà può contenere solo le `Get` routine e della proprietà `Set` tra l' [istruzione Property](property-statement.md) e l' `End Property` istruzione. Non è possibile archiviare un valore diverso da tali procedure. In particolare, non è possibile archiviare il valore corrente della proprietà. È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi. L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../modifiers/private.md) dichiarata allo stesso livello della proprietà. È necessario definire una `Get` routine all'interno della proprietà a cui si applica.  
  
 `Get`Per impostazione predefinita, la procedura viene impostata sul livello di accesso della proprietà che lo contiene, a meno che non si utilizzi `accessmodifier` nell' `Get` istruzione.  
  
## <a name="rules"></a>Regole  
  
- **Livelli di accesso misti.** Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la `Get` routine o `Set` , ma non per entrambi. In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà. Se, ad esempio, la proprietà è dichiarata `Friend` , è possibile dichiarare la `Get` routine `Private` , ma non `Public` .  
  
     Se si definisce una `ReadOnly` proprietà, la `Get` routine rappresenta l'intera proprietà. Non è possibile dichiarare un livello di accesso diverso per `Get` , perché in questo caso verrebbero impostati due livelli di accesso per la proprietà.  
  
- **Tipo restituito.** L' [istruzione Property](property-statement.md) può dichiarare il tipo di dati del valore restituito. La `Get` stored procedure restituisce automaticamente il tipo di dati. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.  
  
     Se l' `Property` istruzione non specifica `returntype` , la procedura restituisce `Object` .  
  
## <a name="behavior"></a>Comportamento  
  
- **Restituzione da una routine.** Quando la `Get` procedura viene restituita al codice chiamante, l'esecuzione continua all'interno dell'istruzione che ha richiesto il valore della proprietà.  
  
     `Get`le routine Property possono restituire un valore utilizzando l' [istruzione return](return-statement.md) o assegnando il valore restituito al nome della proprietà. Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](function-statement.md).  
  
     Le `Exit Property` `Return` istruzioni e generano un'uscita immediata da una routine di proprietà. Qualsiasi numero di `Exit Property` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Property` `Return` istruzioni e.  
  
- **Valore restituito.** Per restituire un valore da una `Get` routine, è possibile assegnare il valore al nome della proprietà o includerlo in un' [istruzione Return](return-statement.md). L' `Return` istruzione assegna simultaneamente il `Get` valore restituito della routine e chiude la procedura.  
  
     Se si utilizza `Exit Property` senza assegnare un valore al nome della proprietà, la `Get` stored procedure restituisce il valore predefinito per il tipo di dati della proprietà. Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](function-statement.md).  
  
     Nell'esempio seguente vengono illustrati due modi in cui la proprietà `quoteForTheDay` di sola lettura può restituire il valore contenuto nella variabile privata `quoteValue` .  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Get` istruzione per restituire il valore di una proprietà.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione set](set-statement.md)
- [Property Statement](property-statement.md)
- [Istruzione Exit](exit-statement.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
- [Procedura dettagliata: definizione delle classi](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
