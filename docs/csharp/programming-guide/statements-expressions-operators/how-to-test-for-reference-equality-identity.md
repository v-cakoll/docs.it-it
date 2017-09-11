---
title: "Procedura: testare l'uguaglianza di riferimenti (identità) (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a115abe599f45163c0d7e6a31dd1dab3e9c06c4b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="1033f-102">Procedura: testare l'uguaglianza di riferimenti (identità) (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1033f-102">How to: Test for Reference Equality (Identity) (C# Programming Guide)</span></span>
<span data-ttu-id="1033f-103">Non è necessario implementare alcuna logica personalizzata per supportare i confronti di uguaglianza dei riferimenti nei tipi.</span><span class="sxs-lookup"><span data-stu-id="1033f-103">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="1033f-104">Questa funzionalità viene fornita per tutti i tipi dal metodo statico <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1033f-104">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="1033f-105">L'esempio seguente mostra come determinare se due variabili presentano *uguaglianza dei riferimenti*, ovvero se fanno riferimento allo stesso oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="1033f-105">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="1033f-106">Nell'esempio viene inoltre illustrato perché <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> restituisce sempre `false` per i tipi di valore e perché non è consigliabile utilizzare <xref:System.Object.ReferenceEquals%2A> per determinare l'uguaglianza di stringhe.</span><span class="sxs-lookup"><span data-stu-id="1033f-106">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1033f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="1033f-107">Example</span></span>  
 <span data-ttu-id="1033f-108">[!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1033f-108">[!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]</span></span>  
  
 <span data-ttu-id="1033f-109">L'implementazione di `Equals` nella classe di base universale <xref:System.Object?displayProperty=fullName> esegue anche un controllo dell'uguaglianza dei riferimenti, ma è meglio non servirsene perché, se una classe esegue l'override del metodo, i risultati potrebbero non essere quelli previsti.</span><span class="sxs-lookup"><span data-stu-id="1033f-109">The implementation of `Equals` in the <xref:System.Object?displayProperty=fullName> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="1033f-110">Lo stesso vale per gli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="1033f-110">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="1033f-111">Quando si opera sui tipi di riferimento, il comportamento predefinito di == e `!=` prevede l'esecuzione di un controllo dell'uguaglianza dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="1033f-111">When they are operating on reference types, the default behavior of == and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="1033f-112">Le classi derivate possono tuttavia eseguire l'overload dell'operatore per eseguire un controllo dell'uguaglianza dei valori.</span><span class="sxs-lookup"><span data-stu-id="1033f-112">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="1033f-113">Per ridurre al minimo la possibilità di errori, è preferibile usare sempre <xref:System.Object.ReferenceEquals%2A> quando è necessario determinare se due oggetti presentano uguaglianza dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="1033f-113">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="1033f-114">Stringhe costanti all'interno dello stesso assembly vengono sempre archiviate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="1033f-114">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="1033f-115">Ciò significa che viene mantenuta una sola istanza di ogni stringa letterale univoca.</span><span class="sxs-lookup"><span data-stu-id="1033f-115">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="1033f-116">Il runtime tuttavia non garantisce che le stringhe create in fase di esecuzione vengano archiviate né garantisce che due stringhe costanti uguali in assembly diversi vengano centralizzate.</span><span class="sxs-lookup"><span data-stu-id="1033f-116">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1033f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1033f-117">See Also</span></span>  
 [<span data-ttu-id="1033f-118">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="1033f-118">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)

