---
title: "Metodi e proprietà di overload (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Metodi e proprietà di overload (Visual Basic)
Eseguire l'overload è la creazione di più di una stored procedure, il costruttore di istanza o proprietà in una classe con lo stesso nome ma con diversi tipi di argomento.  
  
## <a name="overloading-usage"></a>Utilizzo dell'overload  
 L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano sui tipi di dati diversi. Ad esempio, una classe che è possibile visualizzare diversi tipi di dati è può presentare `Display` procedure simili al seguente:  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Senza l'overload, è necessario creare nomi distinti per ogni procedura, anche se eseguono la stessa operazione, come indicato di seguito:  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 L'overload, è facile usare metodi o proprietà, perché fornisce una scelta dei tipi di dati che può essere utilizzato. Ad esempio, il metodo di overload `Display` metodo descritto in precedenza può essere chiamato con una delle righe di codice seguenti:  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 In fase di esecuzione [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] specifica chiama la stored procedure corretta dipende dai tipi di dati dei parametri.  
  
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
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Per usare questo esempio per creare un metodo di overload  
  
1.  Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.  
  
2.  Aggiungere il codice seguente alla classe `TaxClass`.  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Aggiungere la procedura seguente al form.  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Aggiungere un pulsante al form e chiamare il `ShowTax` stored procedure di `Button1_Click` evento del pulsante.  
  
5.  Eseguire il progetto e fare clic sul pulsante sul form per testare il metodo di overload `ShowTax` stored procedure.  
  
 In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati. Quando si fa clic sul pulsante, viene chiamato prima con il metodo di overload un `Price` parametro che è una stringa e il messaggio "prezzo è una stringa. Imposta è $5.12" viene visualizzato. `TaxAmount`viene chiamato con un `Decimal` la seconda volta e il messaggio di valore, "prezzo è un numero decimale. Imposta è $5.12" viene visualizzato.  
  
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
