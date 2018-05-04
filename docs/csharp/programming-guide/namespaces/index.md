---
title: Spazi dei nomi (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="namespaces-c-programming-guide"></a>Spazi dei nomi (Guida per programmatori C#)
Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi. Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi. Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 Per altre informazioni, vedere la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi. Usare la parola chiave [namespace](../../../csharp/language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a>Panoramica degli spazi dei nomi  
 Gli spazi dei nomi hanno le proprietà riportate di seguito:  
  
-   Consentono di organizzare progetti di codice di grandi dimensioni.  
  
-   Vengono delimitati usando l'operatore `.`.  
  
-   `using directive` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.  
  
-   Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi `System` di .NET Framework.  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per altre informazioni sugli spazi dei nomi, vedere gli argomenti seguenti:  
  
-   [Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Procedura: Usare l'alias dello spazio dei nomi globale](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Procedura: Usare lo spazio dei nomi My](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [Direttiva using](../../../csharp/language-reference/keywords/using-directive.md)  
 [Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [. (operatore)](../../../csharp/language-reference/operators/member-access-operator.md)
