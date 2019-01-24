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
ms.openlocfilehash: 0e8ec5877cba5f5cf97e1677460da06fd87cce1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587554"
---
# <a name="new-operator-visual-basic"></a>Operatore New (Visual Basic)
Introduce un `New` clausola per creare una nuova istanza dell'oggetto, specifica un vincolo di costruttore su un parametro di tipo oppure identifica un `Sub` procedure come un costruttore di classe.  
  
## <a name="remarks"></a>Note  
 In una dichiarazione o istruzione di assegnazione, un `New` clausola deve specificare una classe definita da cui è possibile creare l'istanza. Ciò significa che la classe deve esporre uno o più costruttori che il codice chiamante può accedere.  
  
 È possibile usare un `New` clausola in un'istruzione di dichiarazione o un'istruzione di assegnazione. Quando viene eseguita l'istruzione, chiama il costruttore appropriato della classe specificata, vengono passati gli argomenti forniti. Nell'esempio seguente viene illustrata questa mediante la creazione di istanze di un `Customer` classe che dispone di due costruttori, uno che non accetta parametri e uno che accetta un parametro di stringa.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Poiché le matrici sono classi, `New` può creare una nuova istanza di matrice, come illustrato negli esempi seguenti.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Common language runtime (CLR) genera un <xref:System.OutOfMemoryException> errore se è disponibile memoria sufficiente per creare la nuova istanza.  
  
> [!NOTE]
>  Il `New` (parola chiave) viene inoltre utilizzato in elenchi di parametri di tipo per specificare che il tipo fornito deve esporre un costruttore senza parametri accessibile. Per altre informazioni sui parametri di tipo e sui vincoli, vedere [elenco di tipi](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave). Per altre informazioni, vedere [durata degli oggetti: Come gli oggetti vengono creati e distrutti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 È possibile usare la parola chiave `New` nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.OutOfMemoryException>
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Durata degli oggetti: Come gli oggetti vengono creati ed eliminati](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
