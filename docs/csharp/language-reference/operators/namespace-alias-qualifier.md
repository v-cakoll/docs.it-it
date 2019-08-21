---
title: 'Operatore :: - Riferimenti per C#'
ms.custom: seodec18
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2aceb51747708b12fb3059b097b72206c78a9d5d
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971234"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c34d6-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c34d6-102">:: operator (C# reference)</span></span>

<span data-ttu-id="c34d6-103">Usare il qualificatore di alias dello spazio dei nomi `::` per accedere ai membri di uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="c34d6-103">Use the namespace alias qualifier `::` to access members of an aliased namespace.</span></span> <span data-ttu-id="c34d6-104">Il qualificatore `::` viene usato tra due identificatori.</span><span class="sxs-lookup"><span data-stu-id="c34d6-104">You use the `::` qualifier between two identifiers.</span></span> <span data-ttu-id="c34d6-105">L'identificatore a sinistra può essere uno qualsiasi degli alias seguenti:</span><span class="sxs-lookup"><span data-stu-id="c34d6-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="c34d6-106">Un alias dello spazio dei nomi creato con la [direttiva alias using](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="c34d6-106">A namespace alias created with the [using alias directive](../keywords/using-directive.md):</span></span>
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="c34d6-107">Un [alias extern](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="c34d6-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="c34d6-108">L'alias `global`, ovvero l'alias dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="c34d6-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="c34d6-109">Lo spazio dei nomi globale è lo spazio dei nomi che contiene gli spazi dei nomi e i tipi non dichiarati all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="c34d6-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="c34d6-110">Quando viene usato con il qualificatore `::`, l'alias `global` fa sempre riferimento allo spazio dei nomi globale, anche se è presente l'alias dello spazio dei nomi `global` definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c34d6-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>
  
  <span data-ttu-id="c34d6-111">Nell'esempio seguente viene usato l'alias `global` per accedere allo spazio dei nomi .NET <xref:System>, che è un membro dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="c34d6-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="c34d6-112">Senza l'alias `global`, verrà eseguito l'accesso allo spazio dei nomi `System` definito dall'utente, che è un membro dello spazio dei nomi `MyCompany.MyProduct`:</span><span class="sxs-lookup"><span data-stu-id="c34d6-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }
  
      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```
  
  > [!NOTE]
  > <span data-ttu-id="c34d6-113">La parola chiave `global` è l'alias dello spazio dei nomi globale solo quando è l'identificatore di sinistra del qualificatore `::`.</span><span class="sxs-lookup"><span data-stu-id="c34d6-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="c34d6-114">È anche possibile usare l'[operatore di accesso ai membri `.`](member-access-operators.md#member-access-operator-) per accedere ai membri di uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="c34d6-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access members of an aliased namespace.</span></span> <span data-ttu-id="c34d6-115">L'operatore `.` viene tuttavia anche usato per accedere ai membri di un tipo.</span><span class="sxs-lookup"><span data-stu-id="c34d6-115">However, the `.` operator is also used to access members of a type.</span></span> <span data-ttu-id="c34d6-116">Il qualificatore `::` garantisce che il relativo identificatore di sinistra faccia sempre riferimento a un alias dello spazio dei nomi, anche se esiste un tipo o uno spazio dei nomi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c34d6-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c34d6-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c34d6-117">C# language specification</span></span>

<span data-ttu-id="c34d6-118">Per altre informazioni, vedere la sezione [Qualificatori di alias dello spazio dei nomi](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c34d6-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c34d6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c34d6-119">See also</span></span>

- [<span data-ttu-id="c34d6-120">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c34d6-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c34d6-121">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c34d6-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="c34d6-122">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c34d6-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
