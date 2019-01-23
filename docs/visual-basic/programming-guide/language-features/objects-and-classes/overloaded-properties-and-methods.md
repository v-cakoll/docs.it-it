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
ms.openlocfilehash: 472cd0dbfc0544477d8e368b553a454b977d633c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498609"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Proprietà di overload e i metodi (Visual Basic)

L'overload è la creazione di più di una routine, costruttore di istanza o proprietà in una classe con lo stesso nome ma con tipi di argomenti diversi.  
  
## <a name="overloading-usage"></a>Utilizzo dell'overload

 L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano sui tipi di dati diversi. Ad esempio, una classe in grado di visualizzare diversi tipi di dati può presentare `Display` procedure con un aspetto simile al seguente:  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 Senza l'overload, è necessario creare nomi distinti per ogni procedura, anche se fanno la stessa cosa, come indicato di seguito:  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 L'overload rende più semplice usare metodi o proprietà in quanto fornisce una scelta dei tipi di dati che può essere utilizzato. Ad esempio, di overload `Display` metodo descritto in precedenza può essere chiamato con una qualsiasi delle righe di codice seguenti:  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 In fase di esecuzione, Visual Basic chiama la stored procedure corretta in base ai tipi di dati dei parametri specificati.  
  
## <a name="overloading-rules"></a>Regole di overload

 Si crea un membro di overload per una classe mediante l'aggiunta di due o più proprietà o metodi con lo stesso nome. Ad eccezione dei membri derivati, ogni membro di overload deve avere diversi elenchi di parametri e gli elementi seguenti non possono essere utilizzati come caratteristica di differenziazione l'overload di una proprietà o routine:  
  
-   I modificatori, ad esempio `ByVal` o `ByRef`, che si applicano a un membro o i parametri del membro.  
  
-   Nomi dei parametri  
  
-   Restituisce i tipi di procedure  
  
 Il `Overloads` parola chiave è facoltativa quando l'overload, ma se uno qualsiasi di overload membro utilizza il `Overloads` (parola chiave) e quindi tutti gli altri membri in overload con lo stesso nome anche necessario specificare questa parola chiave.  
  
 Le classi derivate possono eseguire l'overload di membri ereditati con i membri che hanno parametri identici e i tipi di parametro, un processo noto come *shadowing in base al nome e firma*. Se il `Overloads` parola chiave viene usata quando shadowing in base al nome e firma, l'implementazione della classe derivata del membro verrà usata al posto di implementazione nella classe di base, e sarà disponibile per le istanze di tutti gli altri overload per il membro di classe derivata.  
  
 Se il `Overloads` parola chiave viene omessa l'overload di un membro ereditato con un membro che dispone di parametri identici e tipi di parametro, quindi viene chiamato l'overload *shadowing in base al nome*. Shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende non disponibile per le istanze della classe derivata e i relativi discendenti tutti gli altri overload.  
  
 Il `Overloads` e `Shadows` modificatori non sono usati con la proprietà o metodo di stesso.  
  
### <a name="example"></a>Esempio

 L'esempio seguente crea metodi di overload che accettano un `String` o `Decimal` rappresentazione di un importo in dollari e restituiscono una stringa contenente l'IVA.  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Usare questo esempio per creare un metodo di overload
  
1.  Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.  
  
2.  Aggiungere il codice seguente alla classe `TaxClass` .  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  Aggiungere la procedura seguente al form.  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  Aggiungere un pulsante al form e chiamare il `ShowTax` procedure dal `Button1_Click` evento del pulsante.  
  
5.  Eseguire il progetto e fare clic sul pulsante nel modulo per eseguire il test di overload `ShowTax` procedure.  
  
 In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri in uso. Quando si fa clic sul pulsante, il metodo di overload viene chiamato prima di tutto con un `Price` parametro che è una stringa e il messaggio, "prezzo è una stringa. L'imposta è $5,12" viene visualizzato. `TaxAmount` viene chiamato con un `Decimal` la seconda volta e il messaggio di valore, "prezzo è un numero decimale. L'imposta è $5,12" viene visualizzato.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
