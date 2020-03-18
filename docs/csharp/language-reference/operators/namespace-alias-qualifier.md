---
title: 'Operatore :: - Riferimenti per C#'
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
ms.openlocfilehash: a18e52ea05d49bf2b3a468923f1433f09fff9a8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712676"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="518a0-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="518a0-102">:: operator (C# reference)</span></span>

<span data-ttu-id="518a0-103">Utilizzare il qualificatore `::` di alias dello spazio dei nomi per accedere a un membro di uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="518a0-103">Use the namespace alias qualifier `::` to access a member of an aliased namespace.</span></span> <span data-ttu-id="518a0-104">È possibile `::` utilizzare il qualificatore solo tra due identificatori.</span><span class="sxs-lookup"><span data-stu-id="518a0-104">You can use the `::` qualifier only between two identifiers.</span></span> <span data-ttu-id="518a0-105">L'identificatore a sinistra può essere uno qualsiasi degli alias seguenti:</span><span class="sxs-lookup"><span data-stu-id="518a0-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="518a0-106">Alias dello spazio dei nomi creato con una [direttiva using alias](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="518a0-106">A namespace alias created with a [using alias directive](../keywords/using-directive.md):</span></span>

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="518a0-107">Un [alias extern](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="518a0-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="518a0-108">L'alias `global`, ovvero l'alias dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="518a0-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="518a0-109">Lo spazio dei nomi globale è lo spazio dei nomi che contiene gli spazi dei nomi e i tipi non dichiarati all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="518a0-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="518a0-110">Quando viene usato con il qualificatore `::`, l'alias `global` fa sempre riferimento allo spazio dei nomi globale, anche se è presente l'alias dello spazio dei nomi `global` definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="518a0-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>

  <span data-ttu-id="518a0-111">Nell'esempio seguente viene usato l'alias `global` per accedere allo spazio dei nomi .NET <xref:System>, che è un membro dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="518a0-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="518a0-112">Senza l'alias `global`, verrà eseguito l'accesso allo spazio dei nomi `System` definito dall'utente, che è un membro dello spazio dei nomi `MyCompany.MyProduct`:</span><span class="sxs-lookup"><span data-stu-id="518a0-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

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
  > <span data-ttu-id="518a0-113">La parola chiave `global` è l'alias dello spazio dei nomi globale solo quando è l'identificatore di sinistra del qualificatore `::`.</span><span class="sxs-lookup"><span data-stu-id="518a0-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="518a0-114">È inoltre possibile utilizzare [l'operatore `.` ](member-access-operators.md#member-access-operator-) di accesso ai membri per accedere a un membro di uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="518a0-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access a member of an aliased namespace.</span></span> <span data-ttu-id="518a0-115">Tuttavia, `.` l'operatore viene utilizzato anche per accedere a un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="518a0-115">However, the `.` operator is also used to access a type member.</span></span> <span data-ttu-id="518a0-116">Il qualificatore `::` garantisce che il relativo identificatore di sinistra faccia sempre riferimento a un alias dello spazio dei nomi, anche se esiste un tipo o uno spazio dei nomi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="518a0-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="518a0-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="518a0-117">C# language specification</span></span>

<span data-ttu-id="518a0-118">Per altre informazioni, vedere la sezione [Qualificatori di alias dello spazio dei nomi](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="518a0-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="518a0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518a0-119">See also</span></span>

- [<span data-ttu-id="518a0-120">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="518a0-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="518a0-121">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="518a0-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="518a0-122">Utilizzo degli spazi dei nomiUsing namespaces</span><span class="sxs-lookup"><span data-stu-id="518a0-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
