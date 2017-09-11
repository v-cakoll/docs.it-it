---
title: "Tipo per la variabile &quot;&lt;NomeVariabile&gt;&quot; non verrà dedotto perché associato a un campo in un ambito contenitore | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42110
- bc42110
dev_langs:
- VB
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 0f954fda84c9fd1a4af5315be2329de117e6d169
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="16cb0-102">Tipo per la variabile '&lt;NomeVariabile&gt;' non verrà dedotto perché associato a un campo in un ambito contenitore</span><span class="sxs-lookup"><span data-stu-id="16cb0-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="16cb0-103">Tipo per la variabile '\<nomevariabile >' non verrà dedotto perché associato a un campo in un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="16cb0-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="16cb0-104">Modificare il nome di '\<nomevariabile >', oppure utilizzare il nome completo (ad esempio, 'Variablename' o 'MyBase').</span><span class="sxs-lookup"><span data-stu-id="16cb0-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="16cb0-105">Una variabile di controllo del ciclo nel codice ha lo stesso nome di un campo della classe o di altro ambito che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="16cb0-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="16cb0-106">Poiché la variabile di controllo viene utilizzata senza un `As` clausola, è associato al campo nell'ambito e il compilatore non creare una nuova variabile per o dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="16cb0-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="16cb0-107">Nell'esempio seguente, `Index`, la variabile di controllo nel `For` istruzione, è associato al `Index` campo la `Customer` classe.</span><span class="sxs-lookup"><span data-stu-id="16cb0-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="16cb0-108">Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="16cb0-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="16cb0-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="16cb0-109">By default, this message is a warning.</span></span> <span data-ttu-id="16cb0-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="16cb0-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="16cb0-111">**ID errore:** BC42110</span><span class="sxs-lookup"><span data-stu-id="16cb0-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="16cb0-112">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="16cb0-112">To address this warning</span></span>  
  
-   <span data-ttu-id="16cb0-113">Rendere la variabile di controllo locale modificando il nome a un identificatore che non è anche il nome di un campo della classe.</span><span class="sxs-lookup"><span data-stu-id="16cb0-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="16cb0-114">Chiarire che la variabile di controllo associata al campo della classe anteponendo `Me.` al nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="16cb0-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="16cb0-115">Anziché affidarsi all'inferenza del tipo locale, utilizzare un `As` clausola per specificare un tipo per la variabile di controllo.</span><span class="sxs-lookup"><span data-stu-id="16cb0-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="16cb0-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="16cb0-116">Example</span></span>  
 <span data-ttu-id="16cb0-117">Il codice seguente viene illustrato l'esempio precedente la correzione prima sul posto.</span><span class="sxs-lookup"><span data-stu-id="16cb0-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="16cb0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cb0-118">See Also</span></span>  
 <span data-ttu-id="16cb0-119">[Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16cb0-119">[Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="16cb0-120"> [Per ogni corso... Next (istruzione)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16cb0-120"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="16cb0-121"> [For... Next (istruzione)](../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16cb0-121"> [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="16cb0-122"> [Procedura: fare riferimento all'istanza corrente di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="16cb0-122"> [How to: Refer to the Current Instance of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="16cb0-123"> [Inferenza del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="16cb0-123"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="16cb0-124"> [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="16cb0-124"> [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

