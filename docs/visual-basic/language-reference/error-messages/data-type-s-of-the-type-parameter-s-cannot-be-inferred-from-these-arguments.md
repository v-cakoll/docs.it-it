---
title: Impossibile dedurre da questi argomenti i tipi di dati dei parametri di tipo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b290c25286dce2236823919e8287db9abefc0dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="4afbb-102">Impossibile dedurre da questi argomenti i tipi di dati dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4afbb-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="4afbb-103">Impossibile dedurre da questi argomenti i tipi di dati dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="4afbb-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="4afbb-104">Per correggere l'errore, provare a specificare i tipi di dati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="4afbb-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="4afbb-105">Questo errore si verifica quando la risoluzione dell'overload non riesce.</span><span class="sxs-lookup"><span data-stu-id="4afbb-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="4afbb-106">Viene visualizzato come messaggio subordinato che indica perché un determinato candidato di overload è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="4afbb-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="4afbb-107">Il messaggio di errore spiega che il compilatore non è possibile usare l'inferenza del tipo per trovare tipi di dati per i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="4afbb-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4afbb-108">Quando non è possibile specificare gli argomenti (ad esempio per gli operatori di query nelle espressioni di query), il messaggio di errore visualizzato non contiene la seconda frase.</span><span class="sxs-lookup"><span data-stu-id="4afbb-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="4afbb-109">Il codice seguente illustra l'errore.</span><span class="sxs-lookup"><span data-stu-id="4afbb-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="4afbb-110">**ID errore:** BC36647 e BC36644</span><span class="sxs-lookup"><span data-stu-id="4afbb-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4afbb-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4afbb-111">To correct this error</span></span>  
  
-   <span data-ttu-id="4afbb-112">È possibile specificare un tipo di dati per il parametro o i parametri di tipo anziché basarsi sull'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4afbb-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afbb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afbb-113">See Also</span></span>  
 [<span data-ttu-id="4afbb-114">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="4afbb-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="4afbb-115">Routine generiche in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4afbb-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="4afbb-116">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4afbb-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
