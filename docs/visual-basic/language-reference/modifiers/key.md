---
title: Chiave
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92c8809779d6cab524f67ee47f355b72ab152403
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351510"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
La parola chiave `Key` consente di specificare il comportamento per le proprietà dei tipi anonimi. Solo le proprietà designate come proprietà chiave partecipano ai test di uguaglianza tra le istanze di tipo anonimo o il calcolo dei valori del codice hash. Non è possibile modificare i valori delle proprietà chiave.  
  
 Per definire una proprietà di un tipo anonimo come proprietà chiave, inserire la parola chiave `Key` davanti alla relativa dichiarazione nell'elenco di inizializzazione. Nell'esempio seguente `Airline` e `FlightNo` sono proprietà chiave, ma `Gate` non lo è.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Quando viene creato un nuovo tipo anonimo, esso eredita direttamente da <xref:System.Object>. Il compilatore esegue l'override di tre membri ereditati: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>e <xref:System.Object.ToString%2A>. Il codice di sostituzione prodotto per <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> si basa sulle proprietà chiave. Se nel tipo non sono presenti proprietà chiave, <xref:System.Object.GetHashCode%2A> e <xref:System.Object.Equals%2A> non vengono sottoposte a override.  
  
## <a name="equality"></a>Uguaglianza  
 Due istanze di tipo anonimo sono uguali se sono istanze dello stesso tipo e se i valori delle relative proprietà chiave sono uguali. Negli esempi seguenti `flight2` è uguale a `flight1` dell'esempio precedente, perché sono istanze dello stesso tipo anonimo e hanno valori corrispondenti per le relative proprietà chiave. Tuttavia, `flight3` non è uguale a `flight1` perché ha un valore diverso per una proprietà chiave, `FlightNo`. L'istanza `flight4` non è dello stesso tipo `flight1` perché designa proprietà diverse come proprietà chiave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Se due istanze sono dichiarate solo con proprietà non chiave, identiche in nome, tipo, ordine e valore, le due istanze non sono uguali. Un'istanza senza proprietà chiave è uguale solo a se stessa.  
  
 Per ulteriori informazioni sulle condizioni in cui due istanze di tipo anonimo sono istanze dello stesso tipo anonimo, vedere [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Calcolo del codice hash  
 Come <xref:System.Object.Equals%2A>, la funzione hash definita in <xref:System.Object.GetHashCode%2A> per un tipo anonimo si basa sulle proprietà chiave del tipo. Negli esempi seguenti viene illustrata l'interazione tra le proprietà chiave e i valori del codice hash.  
  
 Le istanze di un tipo anonimo che hanno gli stessi valori per tutte le proprietà chiave hanno lo stesso valore di codice hash, anche se le proprietà non chiave non hanno valori corrispondenti. L'istruzione seguente restituisce `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Le istanze di un tipo anonimo con valori diversi per una o più proprietà chiave hanno valori di codice hash diversi. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Le istanze di tipi anonimi che designano proprietà diverse come proprietà chiave non sono istanze dello stesso tipo. Hanno valori di codice hash diversi anche quando i nomi e i valori di tutte le proprietà sono uguali. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Valori di sola lettura  
 Non è possibile modificare i valori delle proprietà chiave. Ad esempio, in `flight1` degli esempi precedenti, i campi `Airline` e `FlightNo` sono di sola lettura, ma è possibile modificare `Gate`.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
