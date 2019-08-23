---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965417"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Specifica che una variabile o una proprietà può essere letta ma non scritta.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
  
- **Contesto di dichiarazione.** Si può usare `ReadOnly` solo a livello di modulo. Ciò significa che il contesto di Dichiarazione `ReadOnly` per un elemento deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.  
  
- **Modificatori combinati.** Non è possibile `ReadOnly` specificare `Static` insieme a nella stessa dichiarazione.  
  
- **Assegnazione di un valore.** Il codice che utilizza `ReadOnly` una proprietà non può impostarne il valore. Il codice che ha accesso all'archiviazione sottostante può tuttavia assegnare o modificare il valore in qualsiasi momento.  
  
     È possibile assegnare un valore a una `ReadOnly` variabile solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.  
  
## <a name="when-to-use-a-readonly-variable"></a>Quando usare una variabile di sola lettura  
 In alcune situazioni non è possibile utilizzare un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante. Ad esempio, l' `Const` istruzione potrebbe non accettare il tipo di dati che si desidera assegnare oppure potrebbe non essere possibile calcolare il valore in fase di compilazione con un'espressione costante. Il valore potrebbe non essere ancora noto in fase di compilazione. In questi casi, è possibile usare una `ReadOnly` variabile per mantenere un valore costante.  
  
> [!IMPORTANT]
> Se il tipo di dati della variabile è un tipo di riferimento, ad esempio una matrice o un'istanza di classe, i relativi membri possono essere modificati anche se la `ReadOnly`variabile stessa è. Questa condizione è illustrata nell'esempio seguente.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Quando viene inizializzato, la matrice a `characterArray()` cui fa riferimento include "x", "y" e "z". Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificarne il valore dopo l'inizializzazione, ovvero non è possibile assegnarvi una nuova matrice. Tuttavia, è possibile modificare i valori di uno o più membri della matrice. In seguito a una chiamata alla `changeArrayElement`routine, la matrice `characterArray()` a cui fa riferimento include "x", "M" e "z".  
  
 Si noti che questo comportamento è simile alla dichiarazione di un parametro di routine come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce alla routine di modificare l'argomento chiamante stesso ma ne consente la modifica dei membri.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definita `ReadOnly` una proprietà per la data di assunzione di un dipendente. La classe archivia il valore della proprietà internamente `Private` come variabile e solo il codice all'interno della classe può modificare tale valore. Tuttavia, la proprietà è `Public`e qualsiasi codice in grado di accedere alla classe può leggere la proprietà.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 Il modificatore `ReadOnly` può essere usato nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
