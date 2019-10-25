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
ms.openlocfilehash: c0870f4b056658a22928769c369024cdda24f354
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799044"
---
# <a name="new-operator-visual-basic"></a>Operatore New (Visual Basic)

Introduce una clausola `New` per creare una nuova istanza dell'oggetto, specifica un vincolo del costruttore in un parametro di tipo o identifica una routine `Sub` come costruttore di classe.

## <a name="remarks"></a>Note

In una dichiarazione o un'istruzione di assegnazione, una clausola `New` deve specificare una classe definita dalla quale è possibile creare l'istanza. Questo significa che la classe deve esporre uno o più costruttori a cui il codice chiamante può accedere.

È possibile utilizzare una clausola `New` in un'istruzione di dichiarazione o un'istruzione di assegnazione. Quando l'istruzione viene eseguita, viene chiamato il costruttore appropriato della classe specificata, passando gli argomenti specificati. Nell'esempio seguente viene illustrato questo problema creando istanze di una classe `Customer` con due costruttori, uno che non accetta parametri e uno che accetta un parametro di stringa:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Poiché le matrici sono classi, `New` possibile creare una nuova istanza di matrice, come illustrato nell'esempio seguente:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

Il Common Language Runtime (CLR) genera un errore di <xref:System.OutOfMemoryException> se la memoria disponibile non è sufficiente per creare la nuova istanza.

> [!NOTE]
> La parola chiave `New` viene utilizzata anche negli elenchi di parametri di tipo per specificare che il tipo fornito deve esporre un costruttore senza parametri accessibile. Per ulteriori informazioni sui parametri e i vincoli di tipo, vedere [Type list](../statements/type-list.md).

Per creare una routine del costruttore per una classe, impostare il nome di una routine `Sub` sulla parola chiave `New`. Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

È possibile usare la parola chiave `New` nei contesti seguenti:

- [Istruzione Dim](../statements/dim-statement.md)
- [Of](../statements/of-clause.md)
- [Istruzione Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.OutOfMemoryException>
- [Parole chiave](../keywords/index.md)
- [Elenco dei tipi](../statements/type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Durata degli oggetti: come creare e distruggere oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
