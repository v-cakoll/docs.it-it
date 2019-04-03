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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835557"
---
# <a name="special-characters-in-code-visual-basic"></a>Caratteri speciali nel codice (Visual Basic)
A volte è necessario usare caratteri speciali nel codice, vale a dire, alcuni caratteri non alfabetici o numerici. La punteggiatura e caratteri speciali nel set di caratteri Visual Basic hanno vari utilizzi, dall'organizzazione del testo di programma alla definizione di attività che esegue il compilatore o il programma compilato. Questi caratteri non specificano l'esecuzione di un'operazione.  
  
## <a name="parentheses"></a>Parentesi  
 Utilizzare le parentesi quando si definiscono una routine, ad esempio un `Sub` o `Function`. Tutti gli elenchi di argomenti di procedure è necessario racchiudere tra parentesi. Utilizziamo inoltre le parentesi per l'inserimento di variabili o argomenti in gruppi logici, in particolare per l'override dell'ordine predefinito di precedenza degli operatori in un'espressione complessa. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `d` sia il valore di 8,225 `e` è 3. Il calcolo per `d` Usa la precedenza predefinito degli `/` failover `+` ed è equivalente a `d = b + (c / a)`. Le parentesi per il calcolo per `e` ignorare l'ordine di precedenza predefiniti.  
  
## <a name="separators"></a>Separatori  
 I separatori sono ciò che viene suggerito il nome: consentono di separare le sezioni di codice. In Visual Basic, il carattere separatore sia i due punti (`:`). Usare i separatori quando si desidera includere più istruzioni in una singola riga anziché righe separate. Ciò consente di risparmiare spazio e migliora la leggibilità del codice. Nell'esempio seguente mostra tre istruzioni separate da due punti.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Per altre informazioni, vedere [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 I due punti (`:`) carattere viene utilizzato anche per identificare un'etichetta di istruzione. Per altre informazioni, vedere [Procedura: Etichettare le istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Concatenazione  
 Usare la `&` operatore per *concatenazione*, o il collegamento insieme di stringhe. Non confonderla con la `+` operatore, che vengono sommati i valori numerici. Se si usa il `+` operatore per la concatenazione quando si opera su valori numerici, è possibile ottenere risultati non corretti. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Dopo l'esecuzione del codice precedente, il valore di `resultA` sia il valore di 21,01 `resultB` è "10,0111".  
  
## <a name="member-access-operators"></a>Operatori di accesso ai membri  
 Per accedere a un membro di un tipo, si utilizza il punto (`.`) o un punto esclamativo (`!`) operatore tra il nome del tipo e il nome del membro.  
  
### <a name="dot--operator"></a>Punto (.) Operatore  
 Usare il `.` operatore su una classe, struttura, interfaccia o enumerazione come operatore di accesso di membro. Il membro può essere un campo, proprietà, eventi o metodo. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Punto esclamativo (!) Operatore  
 Usare il `!` operatore solo in una classe o interfaccia come operatore di accesso al dizionario. La classe o interfaccia deve avere una proprietà predefinita che accetta un singolo `String` argomento. Identificatore che segue immediatamente il `!` operatore diventa il valore dell'argomento passato alla proprietà predefinita sotto forma di stringa. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Le tre righe di output `MsgBox` visualizzare il valore tutte `32856`. La prima riga Usa l'accesso alla proprietà tradizionali `index`, il secondo Usa il fatto che `index` è la proprietà predefinita della classe `hasDefault`, e il terzo viene utilizzato l'accesso alla classe dizionario.  
  
 Si noti che il secondo operando del `!` operatore deve essere un valido identificatore Visual Basic non racchiusi tra virgolette doppie (`" "`). In altre parole, è possibile utilizzare un valore letterale stringa o variabile di tipo stringa. La modifica seguente all'ultima line-of-i `MsgBox` chiamata genera un errore perché `"X"` è una stringa letterale racchiusa.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Riferimenti alle raccolte predefinite devono essere espliciti. In particolare, è possibile usare il `!` operatore su una variabile di associazione tardiva.  
  
 Il `!` carattere viene usato anche come il `Single` Digita carattere.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
