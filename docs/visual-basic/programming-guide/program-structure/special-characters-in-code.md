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
ms.openlocfilehash: 95bef937912e35cd828bf0090b4cf48ccb3290cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962468"
---
# <a name="special-characters-in-code-visual-basic"></a>Caratteri speciali nel codice (Visual Basic)
In alcuni casi è necessario usare caratteri speciali nel codice, ovvero caratteri non alfabetici o numerici. La punteggiatura e i caratteri speciali del set di caratteri Visual Basic hanno diversi usi, dall'organizzazione del testo del programma alla definizione delle attività eseguite dal compilatore o dal programma compilato. Questi caratteri non specificano l'esecuzione di un'operazione.  
  
## <a name="parentheses"></a>Parentesi  
 Usare le parentesi quando si definisce una routine, ad esempio `Sub` o. `Function` È necessario racchiudere tra parentesi tutti gli elenchi di argomenti di routine. È inoltre possibile utilizzare le parentesi per inserire variabili o argomenti in gruppi logici, in particolare per eseguire l'override dell'ordine predefinito di precedenza degli operatori in un'espressione complessa. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `d` è 8,225 e il valore di `e` è 3. Il calcolo per `d` utilizza la precedenza predefinita di `/` over `+` ed è equivalente a `d = b + (c / a)`. Le parentesi nel calcolo per `e` eseguono l'override della precedenza predefinita.  
  
## <a name="separators"></a>Separatori  
 I separatori eseguono le operazioni che il nome suggerisce: separano sezioni di codice. In Visual Basic il carattere separatore è costituito dai`:`due punti (). Usare i separatori quando si desidera includere più istruzioni su una sola riga anziché su righe separate. Questo consente di risparmiare spazio e di migliorare la leggibilità del codice. Nell'esempio seguente vengono illustrate tre istruzioni separate da due punti.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Per altre informazioni, vedere [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Il carattere due`:`punti () viene utilizzato anche per identificare un'etichetta di istruzione. Per altre informazioni, vedere [Procedura: Istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)Label.  
  
## <a name="concatenation"></a>Concatenazione  
 Utilizzare l' `&` operatore perla concatenazione o collegare le stringhe. Non confonderla con l' `+` operatore, che somma i valori numerici. Se si utilizza l' `+` operatore per concatenare quando si opera su valori numerici, è possibile ottenere risultati non corretti. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `resultA` è 21,01 e il valore di `resultB` è "10,0111".  
  
## <a name="member-access-operators"></a>Operatori di accesso ai membri  
 Per accedere a un membro di un tipo, usare l'operatore punto`.`() o punto esclamativo (`!`) tra il nome del tipo e il nome del membro.  
  
### <a name="dot--operator"></a>Punto (.) Operator  
 Usare l' `.` operatore in una classe, una struttura, un'interfaccia o un'enumerazione come operatore di accesso ai membri. Il membro può essere un campo, una proprietà, un evento o un metodo. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Punto esclamativo (!) Operator  
 Usare l' `!` operatore solo in una classe o in un'interfaccia come operatore di accesso del dizionario. La classe o l'interfaccia deve avere una proprietà predefinita che accetta un `String` singolo argomento. L'identificatore immediatamente successivo all' `!` operatore diventa il valore dell'argomento passato alla proprietà predefinita sotto forma di stringa. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Le tre righe di output `MsgBox` di tutti visualizzano `32856`il valore. La prima riga usa l'accesso tradizionale alla proprietà `index`, il secondo usa il fatto che `index` è la proprietà predefinita della classe `hasDefault`e la terza usa l'accesso tramite dizionario alla classe.  
  
 Si noti che il secondo operando `!` dell'operatore deve essere un identificatore di Visual Basic valido non racchiuso tra virgolette doppie (`" "`). In altre parole, non è possibile usare un valore letterale stringa o una variabile di stringa. La seguente modifica all'ultima riga della `MsgBox` chiamata genera un errore perché `"X"` è un valore letterale stringa racchiuso.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> I riferimenti alle raccolte predefinite devono essere espliciti. In particolare, non è possibile usare `!` l'operatore su una variabile ad associazione tardiva.  
  
 Il `!` carattere viene utilizzato anche `Single` come carattere di tipo.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
