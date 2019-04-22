---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: e13a773f0b585a5c8803a77c7aaad441d90dfe75
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842304"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Il `Key` (parola chiave) consente di specificare il comportamento per le proprietà di tipi anonimi. Solo le proprietà designate come proprietà chiave fanno parte di test di uguaglianza tra le istanze di tipo anonimo o un calcolo dei valori di codice hash. I valori delle proprietà chiave non possono essere modificati.  
  
 Si definisce una proprietà di un tipo anonimo come proprietà chiave inserendo la parola chiave `Key` davanti relativa dichiarazione nell'elenco di inizializzazione. Nell'esempio riportato di seguito `Airline` e `FlightNo` sono le proprietà di chiave, ma `Gate` non.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Quando viene creato un nuovo tipo anonimo, eredita direttamente da <xref:System.Object>. Il compilatore esegue l'override di tre membri ereditati: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Il codice di prodotto per gli override <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> è basato sulle proprietà chiave. Se non esistono proprietà chiave del tipo, <xref:System.Object.GetHashCode%2A> e <xref:System.Object.Equals%2A> non sottoposto a override.  
  
## <a name="equality"></a>Uguaglianza  
 Due istanze di tipo anonimo sono uguali se sono istanze dello stesso tipo e se i valori delle relative proprietà chiave sono uguali. Negli esempi seguenti `flight2` è uguale a `flight1` dall'esempio precedente perché sono istanze dello stesso anonimo tipo e disporre di valori corrispondenti per le relative proprietà chiave. Tuttavia `flight3` non è uguale a `flight1` perché contiene un valore diverso per una proprietà chiave, `FlightNo`. Istanza `flight4` non è dello stesso tipo `flight1` poiché definiscono le diverse proprietà come proprietà chiave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Se due istanze vengono dichiarate con solo proprietà non chiave, identica nel nome, tipo, ordine e valore, le due istanze non sono uguali. Un'istanza senza proprietà chiave è uguale solo a se stesso.  
  
 Per altre informazioni sulle condizioni in cui due istanze di tipo anonimo sono istanze dello stesso tipo anonimo, vedere [i tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Calcolo del codice hash  
 Ad esempio <xref:System.Object.Equals%2A>, la funzione hash che viene definita in <xref:System.Object.GetHashCode%2A> per un tipo anonimo si basa sulle proprietà del tipo di chiave. Gli esempi seguenti mostrano l'interazione tra le proprietà di chiave e hash di valori di codice.  
  
 Le istanze di un tipo anonimo che hanno gli stessi valori per tutte le proprietà chiave hanno lo stesso valore di codice hash, anche se le proprietà non chiave sono privi di valori corrispondenti. L'istruzione seguente restituisce `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Le istanze di un tipo anonimo che hanno valori diversi per uno o più proprietà di chiave con valori di codice hash diversa. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Le istanze di tipi anonimi che definiscono le diverse proprietà come proprietà chiave non sono istanze dello stesso tipo. Hanno valori di codice hash diverso anche quando i nomi e valori di tutte le proprietà sono uguali. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Valori di sola lettura  
 I valori delle proprietà chiave non possono essere modificati. Ad esempio, nella `flight1` negli esempi precedenti, il `Airline` e `FlightNo` campi sono di sola lettura, ma `Gate` può essere modificato.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
