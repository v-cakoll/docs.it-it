---
title: Me, My, MyBase e MyClass in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3ba634eb28c25f47a0e88c856b916383b6ad15a2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="c45f4-102">Me, My, MyBase e MyClass in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c45f4-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="c45f4-103">`Me`, `My`, `MyBase`, e `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hanno nomi simili, ma scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="c45f4-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="c45f4-104">Viene descritta ciascuna di queste entità per distinguerli.</span><span class="sxs-lookup"><span data-stu-id="c45f4-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="c45f4-105">Me</span><span class="sxs-lookup"><span data-stu-id="c45f4-105">Me</span></span>  
 <span data-ttu-id="c45f4-106">Il `Me` (parola chiave) fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="c45f4-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="c45f4-107">`Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="c45f4-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="c45f4-108">Utilizzando `Me` è particolarmente utile per passare informazioni relative all'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o un modulo.</span><span class="sxs-lookup"><span data-stu-id="c45f4-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="c45f4-109">Ad esempio, si supponga di che avere la seguente procedura in un modulo.</span><span class="sxs-lookup"><span data-stu-id="c45f4-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="c45f4-110">È possibile chiamare la routine e passare l'istanza corrente della <xref:System.Windows.Forms.Form>classe come un argomento tramite l'istruzione seguente.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="c45f4-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="c45f4-111">My</span><span class="sxs-lookup"><span data-stu-id="c45f4-111">My</span></span>  
 <span data-ttu-id="c45f4-112">Il `My` funzionalità fornisce un accesso semplice e intuitivo per un numero di [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classi, consentendo il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utente di interagire con il computer, applicazioni, impostazioni, risorse e così via.</span><span class="sxs-lookup"><span data-stu-id="c45f4-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes, enabling the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="c45f4-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="c45f4-113">MyBase</span></span>  
 <span data-ttu-id="c45f4-114">Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="c45f4-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="c45f4-115">`MyBase`viene comunemente utilizzato per accedere ai membri di classe di base sottoposti a override o nascosti in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c45f4-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="c45f4-116">`MyBase.New`viene utilizzato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c45f4-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="c45f4-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="c45f4-117">MyClass</span></span>  
 <span data-ttu-id="c45f4-118">Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="c45f4-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="c45f4-119">`MyClass`è simile a `Me`, ma tutte le chiamate al metodo su di essa sono trattate come se fosse il metodo `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="c45f4-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45f4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c45f4-120">See Also</span></span>  
 [<span data-ttu-id="c45f4-121">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="c45f4-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
