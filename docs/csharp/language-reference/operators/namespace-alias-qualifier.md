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
# <a name="-operator-c-reference"></a>Operatore :: (Riferimenti per C#)

Usare il qualificatore di alias dello spazio dei nomi `::` per accedere ai membri di uno spazio dei nomi con alias. Il qualificatore `::` viene usato tra due identificatori. L'identificatore a sinistra può essere uno qualsiasi degli alias seguenti:

- Un alias dello spazio dei nomi creato con la [direttiva alias using](../keywords/using-directive.md):
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- Un [alias extern](../keywords/extern-alias.md).
- L'alias `global`, ovvero l'alias dello spazio dei nomi globale. Lo spazio dei nomi globale è lo spazio dei nomi che contiene gli spazi dei nomi e i tipi non dichiarati all'interno di uno spazio dei nomi denominato. Quando viene usato con il qualificatore `::`, l'alias `global` fa sempre riferimento allo spazio dei nomi globale, anche se è presente l'alias dello spazio dei nomi `global` definito dall'utente.
  
  Nell'esempio seguente viene usato l'alias `global` per accedere allo spazio dei nomi .NET <xref:System>, che è un membro dello spazio dei nomi globale. Senza l'alias `global`, verrà eseguito l'accesso allo spazio dei nomi `System` definito dall'utente, che è un membro dello spazio dei nomi `MyCompany.MyProduct`:

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
  > La parola chiave `global` è l'alias dello spazio dei nomi globale solo quando è l'identificatore di sinistra del qualificatore `::`.

È anche possibile usare l'[operatore di accesso ai membri `.`](member-access-operators.md#member-access-operator-) per accedere ai membri di uno spazio dei nomi con alias. L'operatore `.` viene tuttavia anche usato per accedere ai membri di un tipo. Il qualificatore `::` garantisce che il relativo identificatore di sinistra faccia sempre riferimento a un alias dello spazio dei nomi, anche se esiste un tipo o uno spazio dei nomi con lo stesso nome.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Qualificatori di alias dello spazio dei nomi](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Uso degli spazi dei nomi](../../programming-guide/namespaces/using-namespaces.md)
