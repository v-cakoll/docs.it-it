---
title: 'Procedura: controllare la disponibilità di una variabile'
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
ms.openlocfilehash: 0bfa7fa2bdac4746827884c1dad62734c549a48e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357387"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="4f3f5-102">Procedura: controllare la disponibilità di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f3f5-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="4f3f5-103">Per controllare la disponibilità di una variabile, è necessario specificarne il *livello di accesso*.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="4f3f5-104">Il livello di accesso determina quale codice dispone dell'autorizzazione per la lettura o la scrittura nella variabile.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="4f3f5-105">Per impostazione predefinita, le *variabili membro* (definite a livello di modulo e all'esterno di qualsiasi routine) per l'accesso pubblico, ovvero qualsiasi codice in grado di visualizzarle possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="4f3f5-106">È possibile modificare questa impostazione specificando un modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="4f3f5-107">Le *variabili locali* (definite all'interno di una routine) hanno nominalmente accesso pubblico, anche se solo il codice all'interno della procedura può accedervi.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="4f3f5-108">Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che la contiene.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="4f3f5-109">Per altre informazioni, vedere [livelli di accesso in Visual Basic](access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4f3f5-109">For more information, see [Access levels in Visual Basic](access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="4f3f5-110">Accesso privato e pubblico</span><span class="sxs-lookup"><span data-stu-id="4f3f5-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="4f3f5-111">Per rendere una variabile accessibile solo dall'interno del modulo, della classe o della struttura</span><span class="sxs-lookup"><span data-stu-id="4f3f5-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="4f3f5-112">Inserire l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-112">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4f3f5-113">Includere la parola chiave [private](../../../language-reference/modifiers/private.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-113">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4f3f5-114">È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, ma non dall'esterno.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="4f3f5-115">Per rendere una variabile accessibile da qualsiasi codice in grado di visualizzarlo</span><span class="sxs-lookup"><span data-stu-id="4f3f5-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="4f3f5-116">Per una variabile membro, inserire l' `Dim` istruzione per la variabile all'interno di un modulo, una classe o una struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4f3f5-117">Includere la parola chiave [public](../../../language-reference/modifiers/public.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-117">Include the [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4f3f5-118">È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="4f3f5-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4f3f5-119">-or-</span></span>  
  
1. <span data-ttu-id="4f3f5-120">Per una variabile locale, inserire l' `Dim` istruzione per la variabile all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="4f3f5-121">Non includere la `Public` parola chiave nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4f3f5-122">È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno della procedura, ma non dall'esterno.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="4f3f5-123">Accesso protetto e Friend</span><span class="sxs-lookup"><span data-stu-id="4f3f5-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="4f3f5-124">È possibile limitare il livello di accesso di una variabile alla relativa classe ed eventuali classi derivate o al relativo assembly.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="4f3f5-125">È anche possibile specificare l'Unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata o in un'altra posizione nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="4f3f5-126">È possibile specificare questa Unione combinando `Protected` le `Friend` parole chiave e nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="4f3f5-127">Per rendere una variabile accessibile solo dall'interno della relativa classe e delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="4f3f5-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="4f3f5-128">Inserire l' `Dim` istruzione per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4f3f5-129">Includere la parola chiave [protected](../../../language-reference/modifiers/protected.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-129">Include the [Protected](../../../language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4f3f5-130">È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno della classe, nonché da qualsiasi classe derivata, ma non dall'esterno di alcuna classe nella catena di derivazione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="4f3f5-131">Per rendere una variabile accessibile solo dall'interno dello stesso assembly</span><span class="sxs-lookup"><span data-stu-id="4f3f5-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="4f3f5-132">Inserire l' `Dim` istruzione per la variabile all'interno di un modulo, una classe o una struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4f3f5-133">Includere la parola chiave [Friend](../../../language-reference/modifiers/friend.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-133">Include the [Friend](../../../language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4f3f5-134">È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, nonché da qualsiasi codice nello stesso assembly, ma non dall'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f3f5-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f3f5-135">Example</span></span>  
 <span data-ttu-id="4f3f5-136">Nell'esempio seguente vengono illustrate le dichiarazioni delle variabili con i `Public` `Protected` livelli di accesso,, `Friend` , `Protected Friend` e `Private` .</span><span class="sxs-lookup"><span data-stu-id="4f3f5-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="4f3f5-137">Si noti che quando l' `Dim` istruzione specifica un livello di accesso, non è necessario includere la `Dim` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="4f3f5-138">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f3f5-138">.NET Framework Security</span></span>  
 <span data-ttu-id="4f3f5-139">Più restrittivo è il livello di accesso di una variabile, minore sarà la probabilità che il codice dannoso possa utilizzarlo in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="4f3f5-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3f5-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f3f5-140">See also</span></span>

- [<span data-ttu-id="4f3f5-141">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f3f5-141">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="4f3f5-142">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="4f3f5-142">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="4f3f5-143">Pubblica</span><span class="sxs-lookup"><span data-stu-id="4f3f5-143">Public</span></span>](../../../language-reference/modifiers/public.md)
- [<span data-ttu-id="4f3f5-144">Protetto</span><span class="sxs-lookup"><span data-stu-id="4f3f5-144">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="4f3f5-145">Amico</span><span class="sxs-lookup"><span data-stu-id="4f3f5-145">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="4f3f5-146">Privata</span><span class="sxs-lookup"><span data-stu-id="4f3f5-146">Private</span></span>](../../../language-reference/modifiers/private.md)
