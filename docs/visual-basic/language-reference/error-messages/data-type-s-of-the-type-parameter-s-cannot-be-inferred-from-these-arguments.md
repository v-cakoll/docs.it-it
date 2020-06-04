---
title: Impossibile dedurre da questi argomenti i tipi di dati dei parametri di tipo
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: b278dcc10a8a4e9e67aacdb16dca2588d2ebd0f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409784"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="939d2-102">Impossibile dedurre da questi argomenti i tipi di dati dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="939d2-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>

<span data-ttu-id="939d2-103">Non è possibile dedurre da questi argomenti i tipi di dati dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="939d2-104">Per correggere l'errore, provare a specificare i tipi di dati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="939d2-104">Specifying the data type(s) explicitly might correct this error.</span></span>

<span data-ttu-id="939d2-105">Questo errore si verifica quando la risoluzione dell'overload non riesce.</span><span class="sxs-lookup"><span data-stu-id="939d2-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="939d2-106">Viene visualizzato come messaggio subordinato che indica perché un determinato candidato di overload è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="939d2-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="939d2-107">Il messaggio di errore spiega che il compilatore non può usare l'inferenza del tipo per trovare i tipi di dati per i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-108">Quando non è possibile specificare gli argomenti (ad esempio per gli operatori di query nelle espressioni di query), il messaggio di errore visualizzato non contiene la seconda frase.</span><span class="sxs-lookup"><span data-stu-id="939d2-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>

<span data-ttu-id="939d2-109">Il codice seguente illustra l'errore.</span><span class="sxs-lookup"><span data-stu-id="939d2-109">The following code demonstrates the error.</span></span>

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

<span data-ttu-id="939d2-110">**ID errore:** BC36647 e BC36644</span><span class="sxs-lookup"><span data-stu-id="939d2-110">**Error ID:** BC36647 and BC36644</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="939d2-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="939d2-111">To correct this error</span></span>

<span data-ttu-id="939d2-112">È possibile specificare un tipo di dati per il parametro o i parametri di tipo anziché basarsi sull'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>

## <a name="see-also"></a><span data-ttu-id="939d2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="939d2-113">See also</span></span>

- [<span data-ttu-id="939d2-114">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="939d2-114">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="939d2-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="939d2-115">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="939d2-116">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="939d2-116">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
