---
title: 'Procedura: controllare la disponibilità di una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 27ee5d3405ea24c0754cffa85e9b89b2ac561e42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652168"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="17957-102">Procedura: controllare la disponibilità di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17957-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="17957-103">È possibile controllare la disponibilità di una variabile specificando il relativo *livello di accesso*.</span><span class="sxs-lookup"><span data-stu-id="17957-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="17957-104">Il livello di accesso determina il codice dispone dell'autorizzazione di lettura o scrittura per la variabile.</span><span class="sxs-lookup"><span data-stu-id="17957-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="17957-105">*Variabili membro* (definito a livello di modulo e all'esterno di qualsiasi routine) predefinito per l'accesso pubblico, che significa che qualsiasi codice che possano essere visualizzate può accedervi.</span><span class="sxs-lookup"><span data-stu-id="17957-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="17957-106">È possibile modificare questo specificando un modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="17957-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="17957-107">*Le variabili locali* (definito all'interno di una stored procedure) nominalmente avere accesso pubblico, sebbene sia possibile accedervi solo codice all'interno della routine.</span><span class="sxs-lookup"><span data-stu-id="17957-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="17957-108">Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="17957-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="17957-109">Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="17957-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="17957-110">Accesso pubblico e privato</span><span class="sxs-lookup"><span data-stu-id="17957-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="17957-111">Per rendere accessibile solo dall'interno il modulo, classe o struttura di una variabile</span><span class="sxs-lookup"><span data-stu-id="17957-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="17957-112">Sul posto di [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17957-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="17957-113">Includere il [privata](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17957-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="17957-114">È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non dall'esterno.</span><span class="sxs-lookup"><span data-stu-id="17957-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="17957-115">Per rendere accessibile da qualsiasi codice che può essere visualizzato una variabile</span><span class="sxs-lookup"><span data-stu-id="17957-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="17957-116">Per una variabile membro, inserire il `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17957-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="17957-117">Includere il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17957-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="17957-118">È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.</span><span class="sxs-lookup"><span data-stu-id="17957-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="17957-119">oppure</span><span class="sxs-lookup"><span data-stu-id="17957-119">-or-</span></span>  
  
1.  <span data-ttu-id="17957-120">Per una variabile locale, inserire il `Dim` istruzione per la variabile all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="17957-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="17957-121">Non includere il `Public` parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17957-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="17957-122">È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno della routine, ma non dall'esterno.</span><span class="sxs-lookup"><span data-stu-id="17957-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="17957-123">Protetto e l'accesso Friend</span><span class="sxs-lookup"><span data-stu-id="17957-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="17957-124">È possibile limitare il livello di accesso di una variabile di classe e tutte le classi derivate, o al relativo assembly.</span><span class="sxs-lookup"><span data-stu-id="17957-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="17957-125">È inoltre possibile specificare l'unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata o in qualsiasi altra posizione nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="17957-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="17957-126">A questo scopo è necessario combinare il `Protected` e `Friend` parole chiave nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="17957-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="17957-127">Per rendere accessibile solo dall'interno di classe e tutte le classi derivate di una variabile</span><span class="sxs-lookup"><span data-stu-id="17957-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="17957-128">Sul posto di `Dim` istruzione per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17957-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="17957-129">Includere il [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17957-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="17957-130">Consente di leggere o scrivere alla variabile da un punto qualsiasi all'interno della classe, nonché dall'interno di qualsiasi classe derivata da esso, ma non dall'esterno di qualsiasi classe nella catena di derivazione.</span><span class="sxs-lookup"><span data-stu-id="17957-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="17957-131">Per rendere accessibile solo dall'interno dello stesso assembly di una variabile</span><span class="sxs-lookup"><span data-stu-id="17957-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="17957-132">Sul posto di `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17957-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="17957-133">Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17957-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="17957-134">È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, nonché da qualsiasi codice nello stesso assembly, ma non dall'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="17957-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17957-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="17957-135">Example</span></span>  
 <span data-ttu-id="17957-136">L'esempio seguente mostra le dichiarazioni di variabili con `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private` livelli di accesso.</span><span class="sxs-lookup"><span data-stu-id="17957-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="17957-137">Si noti che quando il `Dim` istruzione specifica un livello di accesso, non è necessario includere il `Dim` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="17957-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="17957-138">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17957-138">.NET Framework Security</span></span>  
 <span data-ttu-id="17957-139">Più restrittivo il livello di accesso di una variabile, minori saranno le probabilità di codice dannoso può rendere non corretto utilizzano di esso.</span><span class="sxs-lookup"><span data-stu-id="17957-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17957-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17957-140">See Also</span></span>  
 [<span data-ttu-id="17957-141">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17957-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="17957-142">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="17957-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="17957-143">Public</span><span class="sxs-lookup"><span data-stu-id="17957-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="17957-144">Protected</span><span class="sxs-lookup"><span data-stu-id="17957-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="17957-145">Friend</span><span class="sxs-lookup"><span data-stu-id="17957-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="17957-146">Private</span><span class="sxs-lookup"><span data-stu-id="17957-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
