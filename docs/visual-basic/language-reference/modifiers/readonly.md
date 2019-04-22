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
ms.openlocfilehash: 6e361cbe89f4c51f28199b008de817c2d48ef326
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825391"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Specifica che una variabile o una proprietà può essere letto ma non è stato scritta.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Si può usare `ReadOnly` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `ReadOnly` elemento deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o procedure.  
  
-   **Modificatori combinati.** Non è possibile specificare `ReadOnly` insieme a `Static` nella stessa dichiarazione.  
  
-   **Assegnazione di un valore.** Utilizzo di codice un `ReadOnly` proprietà non è possibile impostarne il valore. Ma il codice che ha accesso alla risorsa di archiviazione sottostante può assegnare o modificare il valore in qualsiasi momento.  
  
     È possibile assegnare un valore per un `ReadOnly` variabili solo nella relativa dichiarazione o nel costruttore della classe o struttura in cui è definito.  
  
## <a name="when-to-use-a-readonly-variable"></a>Quando usare una variabile di sola lettura  
 Esistono situazioni in cui non è possibile usare una [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) dichiarare e assegnare un valore costante. Ad esempio, il `Const` istruzione potrebbe non accettare il tipo di dati da assegnare o non è in grado di calcolare il valore in fase di compilazione con un'espressione costante. È il valore potrebbe non conoscere in fase di compilazione. In questi casi, è possibile usare un `ReadOnly` variabile per contenere un valore costante.  
  
> [!IMPORTANT]
>  Se il tipo di dati della variabile è un tipo riferimento, ad esempio una matrice o un'istanza della classe, i relativi membri possono essere modificati anche se è la variabile stessa `ReadOnly`. Questa condizione è illustrata nell'esempio seguente.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Durante l'inizializzazione, la matrice a cui punta `characterArray()` conterrà "x", "y" e "z". Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificare il valore dopo l'inizializzazione; ovvero, una nuova matrice non è possibile assegnare a esso. Tuttavia, è possibile modificare i valori di uno o più dei membri della matrice. In seguito a una chiamata alla routine `changeArrayElement`, la matrice a cui punta `characterArray()` conterrà "x", "M" e "z".  
  
 Si noti che questo è simile alla dichiarazione di un parametro di routine [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce la procedura di modificare l'argomento chiamante, ma consente di modificare i relativi membri.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un `ReadOnly` proprietà per la data di assunzione di un dipendente. La classe archivia il valore della proprietà internamente come una `Private` variabile e solo codice all'interno della classe è possibile modificare tale valore. Tuttavia, la proprietà è `Public`, e qualsiasi codice che possa accedere alla classe possa leggere la proprietà.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 Il modificatore `ReadOnly` può essere usato nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
