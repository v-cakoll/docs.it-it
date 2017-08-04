---
title: Spazi dei nomi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
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
ms.openlocfilehash: a45339a4c3320a92c0339b1cad6345a2555ed920
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-c-programming-guide"></a>Spazi dei nomi (Guida per programmatori C#)
Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi. Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:  
  
 [!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi. Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 Per altre informazioni, vedere la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi. Usare la parola chiave [namespace](../../../csharp/language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:  
  
 [!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
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

