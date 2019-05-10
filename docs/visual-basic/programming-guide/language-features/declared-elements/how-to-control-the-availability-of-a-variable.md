---
title: 'Procedura: Controllare la disponibilità di una variabile (Visual Basic)'
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
ms.openlocfilehash: 419f3eed30a5d4b35bcb9dde5242b9092ee9cb79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610494"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="f244b-102">Procedura: Controllare la disponibilità di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f244b-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f244b-103">È possibile controllare la disponibilità di una variabile specificando relativi *livello di accesso*.</span><span class="sxs-lookup"><span data-stu-id="f244b-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="f244b-104">Il livello di accesso determina il tipo di codice dispone dell'autorizzazione per leggere o scrivere nella variabile.</span><span class="sxs-lookup"><span data-stu-id="f244b-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="f244b-105">*Le variabili membro* (definito a livello di modulo e all'esterno di qualsiasi routine) predefinito per l'accesso pubblico, che significa che qualsiasi codice che possa visualizzarli può accedervi.</span><span class="sxs-lookup"><span data-stu-id="f244b-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="f244b-106">È possibile modificare questo specificando un modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="f244b-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="f244b-107">*Le variabili locali* (definito all'interno di una routine) nominalmente hanno accesso pubblico, anche se solo il codice all'interno della routine può accedervi.</span><span class="sxs-lookup"><span data-stu-id="f244b-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="f244b-108">Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="f244b-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="f244b-109">Per altre informazioni, vedere [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f244b-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="f244b-110">Accesso pubblico e privato</span><span class="sxs-lookup"><span data-stu-id="f244b-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="f244b-111">Per rendere accessibile solo dall'interno il modulo, classe o struttura di una variabile</span><span class="sxs-lookup"><span data-stu-id="f244b-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="f244b-112">Sul posto di [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="f244b-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f244b-113">Includere il [privati](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f244b-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f244b-114">È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non da al suo esterno.</span><span class="sxs-lookup"><span data-stu-id="f244b-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="f244b-115">Per rendere accessibile da qualsiasi codice che è possibile visualizzarlo una variabile</span><span class="sxs-lookup"><span data-stu-id="f244b-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="f244b-116">Per una variabile membro, posizionare il `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="f244b-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f244b-117">Includere il [pubbliche](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f244b-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f244b-118">È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.</span><span class="sxs-lookup"><span data-stu-id="f244b-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="f244b-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="f244b-119">-or-</span></span>  
  
1. <span data-ttu-id="f244b-120">Per una variabile locale, posizionare il `Dim` istruzione per la variabile all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="f244b-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="f244b-121">Non includere il `Public` parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f244b-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f244b-122">È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno della routine, ma non da al suo esterno.</span><span class="sxs-lookup"><span data-stu-id="f244b-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="f244b-123">Protetto e l'accesso Friend</span><span class="sxs-lookup"><span data-stu-id="f244b-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="f244b-124">È possibile limitare il livello di accesso di una variabile alla relativa classe e tutte le classi derivate o al relativo assembly.</span><span class="sxs-lookup"><span data-stu-id="f244b-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="f244b-125">È anche possibile specificare l'unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata oppure in qualsiasi altro punto nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="f244b-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="f244b-126">A questo scopo è necessario combinare le `Protected` e `Friend` parole chiave nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f244b-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="f244b-127">Per rendere accessibile solo dall'interno la relativa classe e tutte le classi derivate di una variabile</span><span class="sxs-lookup"><span data-stu-id="f244b-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="f244b-128">Posizione di `Dim` istruzione per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="f244b-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f244b-129">Includere il [protetti](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f244b-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f244b-130">È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno della classe, oltre che dall'interno tutte le classi derivate da quest'ultimo, ma non all'esterno di qualsiasi classe nella catena di derivazione.</span><span class="sxs-lookup"><span data-stu-id="f244b-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="f244b-131">Per rendere accessibile solo da nello stesso assembly in una variabile</span><span class="sxs-lookup"><span data-stu-id="f244b-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="f244b-132">Posizione di `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="f244b-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f244b-133">Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f244b-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f244b-134">È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno di modulo, classe o struttura, nonché da qualsiasi codice nello stesso assembly, ma non all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f244b-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f244b-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="f244b-135">Example</span></span>  
 <span data-ttu-id="f244b-136">L'esempio seguente mostra le dichiarazioni delle variabili con `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private` livelli di accesso.</span><span class="sxs-lookup"><span data-stu-id="f244b-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="f244b-137">Si noti che quando la `Dim` istruzione specifica un livello di accesso, non è necessario includere il `Dim` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="f244b-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="f244b-138">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f244b-138">.NET Framework Security</span></span>  
 <span data-ttu-id="f244b-139">Il più restrittivo del livello di accesso di una variabile, usare minori saranno le probabilità che codice dannoso può rendere non corretta di esso.</span><span class="sxs-lookup"><span data-stu-id="f244b-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f244b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f244b-140">See also</span></span>

- [<span data-ttu-id="f244b-141">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f244b-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f244b-142">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="f244b-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="f244b-143">Public</span><span class="sxs-lookup"><span data-stu-id="f244b-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f244b-144">Protected</span><span class="sxs-lookup"><span data-stu-id="f244b-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f244b-145">Friend</span><span class="sxs-lookup"><span data-stu-id="f244b-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="f244b-146">Private</span><span class="sxs-lookup"><span data-stu-id="f244b-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
