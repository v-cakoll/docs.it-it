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
ms.openlocfilehash: 5b060f5fa0042dfb8ffa6876f5e172d3bcda67a3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396220"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
La `Key` parola chiave consente di specificare il comportamento per le proprietà dei tipi anonimi. Solo le proprietà designate come proprietà chiave partecipano ai test di uguaglianza tra le istanze di tipo anonimo o il calcolo dei valori del codice hash. Non è possibile modificare i valori delle proprietà chiave.  
  
 Per definire una proprietà di un tipo anonimo come proprietà chiave, inserire la parola chiave davanti alla `Key` relativa dichiarazione nell'elenco di inizializzazione. Nell'esempio seguente `Airline` e `FlightNo` sono proprietà chiave, ma non lo `Gate` è.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Quando viene creato un nuovo tipo anonimo, esso eredita direttamente da <xref:System.Object> . Il compilatore esegue l'override di tre membri ereditati: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> e <xref:System.Object.ToString%2A> . Il codice di sostituzione prodotto per <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> si basa sulle proprietà chiave. Se non sono presenti proprietà chiave nel tipo <xref:System.Object.GetHashCode%2A> e <xref:System.Object.Equals%2A> non vengono sottoposte a override.  
  
## <a name="equality"></a>Uguaglianza  
 Due istanze di tipo anonimo sono uguali se sono istanze dello stesso tipo e se i valori delle relative proprietà chiave sono uguali. Negli esempi seguenti `flight2` è uguale all' `flight1` esempio precedente, perché sono istanze dello stesso tipo anonimo e hanno valori corrispondenti per le relative proprietà chiave. Tuttavia, `flight3` non è uguale a `flight1` perché ha un valore diverso per una proprietà chiave `FlightNo` . `flight4`L'istanza non è dello stesso tipo di `flight1` perché designa proprietà diverse come proprietà chiave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Se due istanze sono dichiarate solo con proprietà non chiave, identiche in nome, tipo, ordine e valore, le due istanze non sono uguali. Un'istanza senza proprietà chiave è uguale solo a se stessa.  
  
 Per ulteriori informazioni sulle condizioni in cui due istanze di tipo anonimo sono istanze dello stesso tipo anonimo, vedere [tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Calcolo del codice hash  
 Analogamente <xref:System.Object.Equals%2A> , la funzione hash definita in <xref:System.Object.GetHashCode%2A> per un tipo anonimo si basa sulle proprietà chiave del tipo. Negli esempi seguenti viene illustrata l'interazione tra le proprietà chiave e i valori del codice hash.  
  
 Le istanze di un tipo anonimo che hanno gli stessi valori per tutte le proprietà chiave hanno lo stesso valore di codice hash, anche se le proprietà non chiave non hanno valori corrispondenti. L'istruzione seguente restituisce `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Le istanze di un tipo anonimo con valori diversi per una o più proprietà chiave hanno valori di codice hash diversi. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Le istanze di tipi anonimi che designano proprietà diverse come proprietà chiave non sono istanze dello stesso tipo. Hanno valori di codice hash diversi anche quando i nomi e i valori di tutte le proprietà sono uguali. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Valori di sola lettura  
 Non è possibile modificare i valori delle proprietà chiave. Negli `flight1` esempi precedenti, ad esempio, i `Airline` campi e sono di sola `FlightNo` lettura, ma `Gate` possono essere modificati.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di tipo anonimo](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
