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
ms.openlocfilehash: 748c38835cec83cefe54535f90d40ec3a030e4f4
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250382"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Specifica che una variabile o una proprietà può essere letta ma non scritta.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
  
- **Contesto di dichiarazione.** Si può usare `ReadOnly` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per un elemento `ReadOnly` deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.  
  
- **Modificatori combinati.** Non è possibile specificare `ReadOnly` insieme a `Static` nella stessa dichiarazione.  
  
- **Assegnazione di un valore.** Il codice che utilizza una proprietà `ReadOnly` non può impostarne il valore. Il codice che ha accesso all'archiviazione sottostante può tuttavia assegnare o modificare il valore in qualsiasi momento.  
  
     È possibile assegnare un valore a una variabile `ReadOnly` solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.  
  
## <a name="when-to-use-a-readonly-variable"></a>Quando usare una variabile di sola lettura  
 In alcune situazioni non è possibile utilizzare un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante. Ad esempio, l'istruzione `Const` potrebbe non accettare il tipo di dati che si desidera assegnare oppure potrebbe non essere possibile calcolare il valore in fase di compilazione con un'espressione costante. Il valore potrebbe non essere ancora noto in fase di compilazione. In questi casi, è possibile usare una variabile `ReadOnly` per mantenere un valore costante.  
  
> [!IMPORTANT]
> Se il tipo di dati della variabile è un tipo di riferimento, ad esempio una matrice o un'istanza di classe, i relativi membri possono essere modificati anche se la variabile stessa è `ReadOnly`. Questa condizione è illustrata nell'esempio seguente.  
  
 ```vb
 ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
 Sub ChangeArrayElement()
     characterArray(1) = "M"c
 End Sub
 ```
  
 Quando viene inizializzato, la matrice a cui fa riferimento `characterArray()` include "x", "y" e "z". Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificarne il valore dopo l'inizializzazione. ovvero non è possibile assegnarvi una nuova matrice. Tuttavia, è possibile modificare i valori di uno o più membri della matrice. In seguito a una chiamata alla procedura `ChangeArrayElement`, la matrice a cui fa riferimento `characterArray()` include "x", "M" e "z".
  
 Si noti che questo comportamento è simile alla dichiarazione di un parametro di routine come [ByVal](byval.md), che impedisce alla routine di modificare l'argomento chiamante stesso ma ne consente la modifica dei membri.  
  
## <a name="example"></a>Esempio

Nell'esempio seguente viene definita una proprietà `ReadOnly` per la data di assunzione di un dipendente. La classe archivia il valore della proprietà internamente come variabile `Private` e solo il codice all'interno della classe può modificare tale valore. Tuttavia, la proprietà è `Public` e qualsiasi codice che possa accedere alla classe può leggere la proprietà.
  
[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]
  
Il modificatore `ReadOnly` può essere usato nei contesti seguenti:
  
- [Istruzione Dim](../statements/dim-statement.md) 
- [Istruzione Property](../statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [WriteOnly](writeonly.md)
- [Parole chiave](../keywords/index.md)
