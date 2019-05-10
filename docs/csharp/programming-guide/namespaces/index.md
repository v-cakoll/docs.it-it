---
title: Spazi dei nomi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 6d3b77a506186166c9ad76490ef47f8759c704eb
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452729"
---
# <a name="namespaces-c-programming-guide"></a>Spazi dei nomi (Guida per programmatori C#)

Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi. Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
`System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi. Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
Per altre informazioni, vedere la [direttiva using](../../language-reference/keywords/using-directive.md).  
  
Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi. Usare la parola chiave [namespace](../../language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

Il nome dello spazio dei nomi deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.

## <a name="namespaces-overview"></a>Panoramica degli spazi dei nomi  

Gli spazi dei nomi hanno le proprietà riportate di seguito:  
  
- Consentono di organizzare progetti di codice di grandi dimensioni.  
- Vengono delimitati usando l'operatore `.`.  
- La direttiva `using` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.  
- Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi <xref:System> di .NET.  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Uso degli spazi dei nomi](using-namespaces.md)
- [Procedura: Usare l'alias dello spazio dei nomi globale](how-to-use-the-global-namespace-alias.md)
- [Procedura: Usare lo spazio dei nomi My](how-to-use-the-my-namespace.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
- [Parole chiave per gli spazi dei nomi](../../language-reference/keywords/namespace-keywords.md)
- [Direttiva using](../../language-reference/keywords/using-directive.md)
- [:: (operatore)](../../language-reference/operators/namespace-alias-qualifer.md)
