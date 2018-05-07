---
title: Caratteri speciali nel codice (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 932b38d97b36292e66bfad91a9a3799459d3b73c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="special-characters-in-code-visual-basic"></a>Caratteri speciali nel codice (Visual Basic)
In alcuni casi è necessario usare caratteri speciali nel codice, ovvero i caratteri non alfabetici o numerici. La punteggiatura e caratteri speciali nel set di caratteri Visual Basic presenti diversi utilizzi, dall'organizzazione del testo di programma alla definizione di attività che esegue il compilatore o dal programma compilato. Questi caratteri non specificano l'esecuzione di un'operazione.  
  
## <a name="parentheses"></a>Tra parentesi  
 Utilizzare le parentesi quando si definisce una routine, ad esempio un `Sub` o `Function`. Tutti gli elenchi di argomenti di stored procedure è necessario racchiudere tra parentesi. È inoltre utilizzare parentesi per raggruppare variabili o argomenti in gruppi logici, soprattutto per ignorare l'ordine predefinito di precedenza degli operatori in un'espressione complessa. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `d` è 8,225 e il valore di `e` è 3. Il calcolo di `d` utilizza la precedenza predefinita di `/` su `+` ed equivale a `d = b + (c / a)`. Le parentesi nel calcolo del `e` ignorare l'ordine predefinito.  
  
## <a name="separators"></a>Separatori  
 Separatori si cosa suggerisce il nome stesso: consentono di separare le sezioni di codice. In Visual Basic, il carattere di separazione è i due punti (`:`). Utilizzare i separatori quando si desidera includere più istruzioni in una singola riga anziché righe separate. Questo consente di risparmiare spazio e migliora la leggibilità del codice. Nell'esempio seguente mostra tre istruzioni separate da virgola.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Per ulteriori informazioni, vedere [come: Break e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 I due punti (`:`) carattere viene utilizzato anche per identificare un'etichetta di istruzione. Per ulteriori informazioni, vedere [come: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Concatenazione  
 Utilizzare il `&` operatore per *concatenazione*, o il collegamento di più stringhe. Non confondere con il `+` operatore, che vengono sommati i valori numerici. Se si utilizza il `+` per concatenare quando si opera su valori numerici, è possibile ottenere risultati non corretti. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `resultA` è 21,01 e il valore di `resultB` è "10,0111".  
  
## <a name="member-access-operators"></a>Operatori di accesso ai membri  
 Per accedere a un membro di un tipo, utilizzare il punto (`.`) o punto esclamativo (`!`) (operatore) tra il nome del tipo e il nome del membro.  
  
### <a name="dot--operator"></a>Punto (.) Operatore  
 Utilizzare il `.` operatore su una classe, struttura, interfaccia o enumerazione come un operatore di accesso ai membri. Il membro può essere un campo, proprietà, eventi o metodo. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Punto esclamativo (!) Operatore  
 Utilizzare il `!` operatore solo in una classe o interfaccia come operatore di accesso al dizionario. La classe o interfaccia deve avere una proprietà predefinita che accetta un unico `String` argomento. Identificatore che segue immediatamente il `!` diventa il valore dell'argomento passato alla proprietà predefinita sotto forma di stringa. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Le tre righe di output `MsgBox` tutti di visualizzare il valore `32856`. La prima riga utilizza l'accesso alla proprietà tradizionale `index`, il secondo si avvalgono del fatto che `index` la proprietà predefinita della classe `hasDefault`, e la terza utilizza la classe di accesso del dizionario.  
  
 Si noti che il secondo operando del `!` operatore deve essere un valido identificatore Visual Basic non è racchiuso tra virgolette doppie (`" "`). In altre parole, è possibile utilizzare un valore letterale stringa o una variabile di stringa. La modifica seguente all'ultima riga del `MsgBox` chiamata genera un errore perché `"X"` è una stringa letterale racchiusa.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  I riferimenti alle raccolte predefinite devono essere espliciti. In particolare, non è possibile utilizzare il `!` operatore su una variabile di associazione tardiva.  
  
 Il `!` carattere viene utilizzato anche come il `Single` carattere tipo.  
  
## <a name="see-also"></a>Vedere anche  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
