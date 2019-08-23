---
title: Operatore New (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955875"
---
# <a name="new-operator-visual-basic"></a>Operatore New (Visual Basic)
Introduce una `New` clausola per creare una nuova istanza dell'oggetto, specifica un vincolo del costruttore in un parametro di tipo o `Sub` identifica una routine come costruttore di classe.  
  
## <a name="remarks"></a>Note  
 In una dichiarazione o un'istruzione di assegnazione `New` , una clausola deve specificare una classe definita da cui è possibile creare l'istanza. Questo significa che la classe deve esporre uno o più costruttori a cui il codice chiamante può accedere.  
  
 È possibile utilizzare una `New` clausola in un'istruzione di dichiarazione o un'istruzione di assegnazione. Quando l'istruzione viene eseguita, viene chiamato il costruttore appropriato della classe specificata, passando gli argomenti specificati. Nell'esempio seguente viene illustrato questo problema creando istanze di `Customer` una classe che dispone di due costruttori, uno che non accetta parametri e uno che accetta un parametro di stringa.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Poiché le matrici sono classi, `New` può creare una nuova istanza di matrice, come illustrato negli esempi seguenti.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Il Common Language Runtime (CLR) genera un <xref:System.OutOfMemoryException> errore se la memoria disponibile non è sufficiente per creare la nuova istanza.  
  
> [!NOTE]
> La `New` parola chiave viene usata anche negli elenchi di parametri di tipo per specificare che il tipo fornito deve esporre un costruttore senza parametri accessibile. Per ulteriori informazioni sui parametri e i vincoli di tipo, vedere [Type list](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Per creare una routine del costruttore per una classe, impostare il nome di `Sub` una stored procedure `New` sulla parola chiave. Per ulteriori informazioni, vedere [durata degli oggetti: Modalità di creazione e distruzione](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)degli oggetti.  
  
 È possibile usare la parola chiave `New` nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.OutOfMemoryException>
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Durata degli oggetti: Come vengono creati ed eliminati gli oggetti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
