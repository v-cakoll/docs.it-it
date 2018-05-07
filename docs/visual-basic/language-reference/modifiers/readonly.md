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
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Specifica che una variabile o proprietà può essere letto ma non è stato scritto.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Si può usare `ReadOnly` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `ReadOnly` elemento deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o stored procedure.  
  
-   **Modificatori combinati.** Non è possibile specificare `ReadOnly` assieme `Static` nella stessa dichiarazione.  
  
-   **Assegnazione di un valore.** Utilizzo di codice un `ReadOnly` proprietà non è possibile impostarne il valore. Tuttavia, il codice che ha accesso alla risorsa di archiviazione sottostante può assegnare o modificare il valore in qualsiasi momento.  
  
     È possibile assegnare un valore per un `ReadOnly` variabile solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.  
  
## <a name="when-to-use-a-readonly-variable"></a>Quando utilizzare una variabile di sola lettura  
 Esistono casi in cui è possibile utilizzare un [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante. Ad esempio, il `Const` istruzione potrebbe non accettare il tipo di dati che si desidera assegnare o potrebbe essere in grado di calcolare il valore in fase di compilazione con un'espressione costante. Potrebbe non conoscere anche il valore in fase di compilazione. In questi casi, è possibile utilizzare un `ReadOnly` variabile per contenere un valore costante.  
  
> [!IMPORTANT]
>  Se il tipo di dati della variabile è un tipo riferimento, ad esempio una matrice o un'istanza della classe, i relativi membri possono essere modificati anche se la variabile è `ReadOnly`. Questa condizione è illustrata nell'esempio seguente.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Durante l'inizializzazione, la matrice a cui puntava `characterArray()` conterrà "x", "y" e "z". Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificare il valore dopo l'inizializzazione; ovvero, una nuova matrice non è possibile assegnare a esso. Tuttavia, è possibile modificare i valori di uno o più membri della matrice. In seguito a una chiamata alla procedura `changeArrayElement`, la matrice a cui puntava `characterArray()` conterrà "x", "M" e "z".  
  
 Si noti che è simile alla dichiarazione di un parametro di routine [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce la procedura di modificare l'argomento chiamante, ma consente di modificare i relativi membri.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un `ReadOnly` proprietà per la data di assunzione di un dipendente. La classe archivia il valore della proprietà internamente come una `Private` variabile e solo codice all'interno della classe è possibile modificare questo valore. Tuttavia, la proprietà è `Public`, e qualsiasi codice che è possibile accedere alla classe è possibile leggere la proprietà.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 Il modificatore `ReadOnly` può essere usato nei contesti seguenti:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
