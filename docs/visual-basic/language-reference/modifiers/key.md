---
title: Key (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Il `Key` (parola chiave) consente di specificare il comportamento per le proprietà di tipi anonimi. Solo le proprietà designate come proprietà chiave utilizzate nei test di uguaglianza tra istanze di tipo anonimo o di calcolo dei valori di codice hash. I valori delle proprietà chiave non possono essere modificati.  
  
 Si definisce una proprietà di un tipo anonimo come proprietà chiave inserendo la parola chiave `Key` davanti alla dichiarazione nell'elenco di inizializzazione. Nell'esempio seguente, `Airline` e `FlightNo` sono proprietà chiave, ma `Gate` non.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 Quando viene creato un nuovo tipo anonimo, eredita direttamente da <xref:System.Object>. Il compilatore esegue l'override di tre membri ereditati: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Il codice di prodotto per gli override <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> è basato sulle proprietà chiave. Se non esistono proprietà chiave del tipo, <xref:System.Object.GetHashCode%2A> e <xref:System.Object.Equals%2A> non sottoposto a override.  
  
## <a name="equality"></a>Uguaglianza  
 Due istanze di tipo anonimo sono uguali se sono istanze dello stesso tipo e se i valori delle relative proprietà chiave sono uguali. Negli esempi seguenti, `flight2` è uguale a `flight1` dell'esempio precedente in quanto sono istanze dello stesso anonimo tipo e dispongono di valori corrispondenti per le proprietà chiave. Tuttavia, `flight3` non è uguale a `flight1` perché contiene un valore diverso per una proprietà chiave, `FlightNo`. Istanza `flight4` non è dello stesso tipo `flight1` poiché definiscono diverse proprietà come proprietà chiave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Se due istanze sono dichiarate con solo proprietà non chiave, identica nel nome, tipo, ordine e valore, non le due istanze sono uguali. Un'istanza senza proprietà chiave è uguale solo a se stesso.  
  
 Per ulteriori informazioni sulle condizioni in cui due istanze di tipo anonimo sono istanze dello stesso tipo anonimo, vedere [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Calcolo del codice hash  
 Ad esempio <xref:System.Object.Equals%2A>, la funzione hash è definita in <xref:System.Object.GetHashCode%2A> per un tipo anonimo è basato sulle proprietà del tipo di chiave. Gli esempi seguenti illustrano l'interazione tra le proprietà chiave e hash di valori di codice.  
  
 Le istanze di un tipo anonimo che hanno gli stessi valori per tutte le proprietà chiave hanno lo stesso valore di codice hash, anche se la proprietà non chiave non dispone di valori corrispondenti. L'istruzione seguente restituisce `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Le istanze di un tipo anonimo che hanno valori diversi per uno o più proprietà di chiave hanno valori di codice hash diverso. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Le istanze di tipi anonimi che definiscono diverse proprietà come proprietà chiave non sono istanze dello stesso tipo. Hanno valori di codice hash diverso anche quando i nomi e valori di tutte le proprietà sono uguali. L'istruzione seguente restituisce `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>Valori di sola lettura  
 I valori delle proprietà chiave non possono essere modificati. Ad esempio, in `flight1` negli esempi precedenti, il `Airline` e `FlightNo` i campi sono di sola lettura, ma `Gate` può essere modificato.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Definizione di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
