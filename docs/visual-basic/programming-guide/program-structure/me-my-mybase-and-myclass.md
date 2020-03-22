---
title: Me, My, MyBase e MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400848"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="3bf54-102">Me, My, MyBase e MyClass in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bf54-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="3bf54-103">`Me`, `My` `MyBase`, `MyClass` e in Visual Basic hanno nomi simili, ma scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="3bf54-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="3bf54-104">In questo argomento viene descritta ognuna di queste entità per distinguerle.</span><span class="sxs-lookup"><span data-stu-id="3bf54-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="3bf54-105">Me stesso</span><span class="sxs-lookup"><span data-stu-id="3bf54-105">Me</span></span>  
 <span data-ttu-id="3bf54-106">La `Me` parola chiave fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui il codice è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bf54-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="3bf54-107">`Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="3bf54-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="3bf54-108">L'utilizzo `Me` è particolarmente utile per passare informazioni sull'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="3bf54-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="3bf54-109">Si supponga, ad esempio, di disporre della procedura seguente in un modulo.</span><span class="sxs-lookup"><span data-stu-id="3bf54-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="3bf54-110">È possibile chiamare questa routine e <xref:System.Windows.Forms.Form> passare l'istanza corrente della classe come argomento utilizzando l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="3bf54-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="3bf54-111">My</span><span class="sxs-lookup"><span data-stu-id="3bf54-111">My</span></span>  
 <span data-ttu-id="3bf54-112">La `My` funzionalità consente di accedere in modo semplice e intuitivo a numerose classi .NET Framework, consentendo all'utente di Visual Basic di interagire con il computer, l'applicazione, le impostazioni, le risorse e così via.</span><span class="sxs-lookup"><span data-stu-id="3bf54-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="3bf54-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="3bf54-113">MyBase</span></span>  
 <span data-ttu-id="3bf54-114">La `MyBase` parola chiave si comporta come una variabile oggetto che fa riferimento alla classe base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="3bf54-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="3bf54-115">`MyBase`viene in genere utilizzato per accedere ai membri della classe base sottoposti a override o sottoposti a shadowing in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3bf54-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="3bf54-116">`MyBase.New`viene utilizzato per chiamare in modo esplicito un costruttore di classi base da un costruttore di classi derivate.</span><span class="sxs-lookup"><span data-stu-id="3bf54-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="3bf54-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="3bf54-117">MyClass</span></span>  
 <span data-ttu-id="3bf54-118">La `MyClass` parola chiave si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come originariamente implementata.</span><span class="sxs-lookup"><span data-stu-id="3bf54-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="3bf54-119">`MyClass`è simile `Me`a , ma tutte le chiamate al `NotOverridable`metodo su di esso vengono considerate come se il metodo fosse .</span><span class="sxs-lookup"><span data-stu-id="3bf54-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf54-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bf54-120">See also</span></span>

- [<span data-ttu-id="3bf54-121">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="3bf54-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
