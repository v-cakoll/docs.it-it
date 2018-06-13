---
title: Proprietà di overload e i metodi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652194"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Proprietà di overload e i metodi (Visual Basic)

Eseguire l'overload è la creazione di più di una stored procedure, il costruttore di istanza o proprietà in una classe con lo stesso nome ma con diversi tipi di argomento.  
  
## <a name="overloading-usage"></a>Utilizzo dell'overload

 L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano sui tipi di dati diversi. Ad esempio, una classe che è possibile visualizzare diversi tipi di dati è può presentare `Display` procedure simili al seguente:  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 Senza l'overload, è necessario creare nomi distinti per ogni procedura, anche se eseguono la stessa operazione, come indicato di seguito:  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 L'overload, è facile usare metodi o proprietà, perché fornisce una scelta dei tipi di dati che può essere utilizzato. Ad esempio, il metodo di overload `Display` metodo descritto in precedenza può essere chiamato con una delle righe di codice seguenti:  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 In fase di esecuzione, Visual Basic chiama la stored procedure corretta in base ai tipi di dati dei parametri specificati.  
  
## <a name="overloading-rules"></a>Regole di overload

 Creare un membro di overload per una classe mediante l'aggiunta di due o più proprietà o metodi con lo stesso nome. Ad eccezione dei membri derivati, ogni membro di overload deve avere elenchi di parametri diversi e gli elementi seguenti non possono essere utilizzati come caratteristica di differenziazione quando l'overload di una proprietà o routine:  
  
-   Modificatori, ad esempio `ByVal` o `ByRef`, che si applicano a un membro o i parametri del membro.  
  
-   Nomi dei parametri  
  
-   Tipi restituiti di procedure  
  
 Il `Overloads` parola chiave è facoltativa quando l'overload, ma eventuali overload membro utilizza il `Overloads` (parola chiave), quindi tutti gli altri membri in overload con lo stesso nome devono inoltre specificare questa parola chiave.  
  
 Le classi derivate possono eseguire l'overload di membri ereditati con membri che hanno parametri identici e tipi di parametro, un processo noto come *shadowing in base al nome e firma*. Se il `Overloads` parola chiave viene utilizzata quando shadowing in base al nome e firma, implementazione della classe derivata del membro verrà utilizzato invece di implementazione nella classe base e sarà disponibile per le istanze di tutti gli altri overload per il membro di classe derivata.  
  
 Se il `Overloads` parola chiave viene omessa quando l'overload di un membro ereditato con un membro che dispone di parametri identici e tipi di parametro, quindi viene chiamato l'overload *shadowing in base al nome*. Shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende disponibili per le istanze della classe derivata e i relativi discendenti tutti gli altri overload.  
  
 Il `Overloads` e `Shadows` i modificatori non usati con lo stesso metodo o proprietà.  
  
### <a name="example"></a>Esempio

 L'esempio seguente crea metodi di overload che accettano un `String` o `Decimal` rappresentazione di un importo in dollari e restituiscono una stringa contenente l'imposta sulle vendite.  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Per usare questo esempio per creare un metodo di overload
  
1.  Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.  
  
2.  Aggiungere il codice seguente alla classe `TaxClass`.  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  Aggiungere la procedura seguente al form.  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  Aggiungere un pulsante al form e chiamare il `ShowTax` stored procedure di `Button1_Click` evento del pulsante.  
  
5.  Eseguire il progetto e fare clic sul pulsante sul form per testare il metodo di overload `ShowTax` stored procedure.  
  
 In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati. Quando si fa clic sul pulsante, viene chiamato prima con il metodo di overload un `Price` parametro che è una stringa e il messaggio "prezzo è una stringa. Imposta è $5.12" viene visualizzato. `TaxAmount` viene chiamato con un `Decimal` la seconda volta e il messaggio di valore, "prezzo è un numero decimale. Imposta è $5.12" viene visualizzato.  
  
## <a name="see-also"></a>Vedere anche

 [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
