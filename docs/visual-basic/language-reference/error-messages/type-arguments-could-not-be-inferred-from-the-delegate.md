---
title: Impossibile dedurre argomenti tipo dal delegato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords: BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 57a3a24af32d9eb85a0f905aa3a73a956723b6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="67e3b-102">Impossibile dedurre argomenti tipo dal delegato</span><span class="sxs-lookup"><span data-stu-id="67e3b-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="67e3b-103">Un'istruzione di assegnazione usa `AddressOf` per assegnare l'indirizzo di un oggetto generico a un delegato, ma non fornisce alcun argomento di tipo alla routine generica.</span><span class="sxs-lookup"><span data-stu-id="67e3b-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="67e3b-104">Di norma, quando si richiama un tipo generico, si fornisce un argomento di tipo per ogni parametro di tipo definito dal tipo generico.</span><span class="sxs-lookup"><span data-stu-id="67e3b-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="67e3b-105">Se non si specifica alcun argomento di tipo, il compilatore prova a dedurre i tipi da passare ai parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="67e3b-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="67e3b-106">Se il contesto non fornisce informazioni sufficienti per consentire al compilatore di dedurre i tipi, genera un errore.</span><span class="sxs-lookup"><span data-stu-id="67e3b-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="67e3b-107">**ID errore:** BC36564</span><span class="sxs-lookup"><span data-stu-id="67e3b-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="67e3b-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="67e3b-108">To correct this error</span></span>  
  
-   <span data-ttu-id="67e3b-109">Specificare gli argomenti di tipo per la routine generica nell'espressione `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="67e3b-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e3b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67e3b-110">See Also</span></span>  
 [<span data-ttu-id="67e3b-111">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67e3b-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="67e3b-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="67e3b-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="67e3b-113">Routine generiche in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67e3b-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="67e3b-114">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="67e3b-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="67e3b-115">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="67e3b-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
