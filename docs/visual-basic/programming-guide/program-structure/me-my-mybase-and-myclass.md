---
title: Me, My, MyBase e MyClass in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bebf404cd65d1b3a2c4059d3a7c986f0157dfe2d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="57f07-102">Me, My, MyBase e MyClass in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57f07-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="57f07-103">`Me`, `My`, `MyBase`, e `MyClass` in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] con nomi simili, ma scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="57f07-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="57f07-104">Questo argomento descrive ognuna di queste entità per distinguerli.</span><span class="sxs-lookup"><span data-stu-id="57f07-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="57f07-105">Me</span><span class="sxs-lookup"><span data-stu-id="57f07-105">Me</span></span>  
 <span data-ttu-id="57f07-106">Il `Me` (parola chiave) fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="57f07-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="57f07-107">`Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="57f07-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="57f07-108">Utilizzando `Me` è particolarmente utile per passare le informazioni sull'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="57f07-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="57f07-109">Ad esempio, si supponga la procedura seguente in un modulo.</span><span class="sxs-lookup"><span data-stu-id="57f07-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="57f07-110">È possibile chiamare la routine e passare l'istanza corrente del <xref:System.Windows.Forms.Form> classe come un argomento tramite l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="57f07-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="57f07-111">My</span><span class="sxs-lookup"><span data-stu-id="57f07-111">My</span></span>  
 <span data-ttu-id="57f07-112">Il `My` fornisce un accesso semplice e intuitivo per un numero di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classi, l'abilitazione di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per interagire con il computer, applicazioni, impostazioni, risorse e così via.</span><span class="sxs-lookup"><span data-stu-id="57f07-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes, enabling the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="57f07-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="57f07-113">MyBase</span></span>  
 <span data-ttu-id="57f07-114">Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="57f07-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="57f07-115">`MyBase`viene comunemente utilizzato per accedere ai membri di classe di base che vengono sottoposti a override o shadowing in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="57f07-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="57f07-116">`MyBase.New`viene utilizzato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="57f07-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="57f07-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="57f07-117">MyClass</span></span>  
 <span data-ttu-id="57f07-118">Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="57f07-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="57f07-119">`MyClass`è simile a `Me`, ma tutte le chiamate al metodo su di essa vengono considerate come se fosse il metodo `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="57f07-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f07-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57f07-120">See Also</span></span>  
 [<span data-ttu-id="57f07-121">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="57f07-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
