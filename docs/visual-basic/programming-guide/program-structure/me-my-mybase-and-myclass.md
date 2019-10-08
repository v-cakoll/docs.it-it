---
title: Me, My, MyBase e MyClass in Visual Basic
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
ms.openlocfilehash: 7df146e09a1d7cd730f4cf539d6823f7ced44bd1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002541"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="0549d-102">Me, My, MyBase e MyClass in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0549d-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="0549d-103">`Me`, `My`, `MyBase` e `MyClass` in Visual Basic hanno nomi simili, ma a scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="0549d-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="0549d-104">In questo argomento vengono descritte le singole entità per distinguerle.</span><span class="sxs-lookup"><span data-stu-id="0549d-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="0549d-105">Me</span><span class="sxs-lookup"><span data-stu-id="0549d-105">Me</span></span>  
 <span data-ttu-id="0549d-106">La parola chiave `Me` fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="0549d-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="0549d-107">`Me` si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="0549d-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="0549d-108">L'uso di `Me` è particolarmente utile per passare informazioni sull'istanza attualmente in esecuzione di una classe o di una struttura a una routine in un'altra classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="0549d-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="0549d-109">Si supponga, ad esempio, di avere la procedura seguente in un modulo.</span><span class="sxs-lookup"><span data-stu-id="0549d-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="0549d-110">È possibile chiamare questa procedura e passare l'istanza corrente della classe <xref:System.Windows.Forms.Form> come argomento usando l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="0549d-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="0549d-111">My</span><span class="sxs-lookup"><span data-stu-id="0549d-111">My</span></span>  
 <span data-ttu-id="0549d-112">La funzionalità `My` consente di accedere in modo semplice e intuitivo a diverse classi .NET Framework, consentendo al Visual Basic utente di interagire con il computer, l'applicazione, le impostazioni, le risorse e così via.</span><span class="sxs-lookup"><span data-stu-id="0549d-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="0549d-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="0549d-113">MyBase</span></span>  
 <span data-ttu-id="0549d-114">La parola chiave `MyBase` si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="0549d-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="0549d-115">`MyBase` viene comunemente usato per accedere ai membri della classe di base sottoposti a override o nascosti in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0549d-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="0549d-116">`MyBase.New` viene usato per chiamare in modo esplicito un costruttore della classe base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0549d-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="0549d-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="0549d-117">MyClass</span></span>  
 <span data-ttu-id="0549d-118">La parola chiave `MyClass` si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="0549d-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="0549d-119">`MyClass` è simile a `Me`, ma tutte le chiamate al metodo su di essa sono trattate come se il metodo fosse `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="0549d-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0549d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0549d-120">See also</span></span>

- [<span data-ttu-id="0549d-121">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="0549d-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
