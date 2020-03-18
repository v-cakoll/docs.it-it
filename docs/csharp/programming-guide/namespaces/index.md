---
title: Spazi dei nomi - Guida per programmatori C#
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 21452e259596c9ab10b3d653ec1d8fb90fad131d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937618"
---
# <a name="namespaces-c-programming-guide"></a>Spazi dei nomi (Guida per programmatori C#)

Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi. In primo luogo, .NET utilizza gli spazi dei nomi per organizzare le molte classi, come indicato di seguito:First, .NET uses namespaces to organize its many classes, as follows:  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<xref:System> è uno spazio dei nomi e <xref:System.Console> è una classe in quello spazio dei nomi. Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]

Per altre informazioni, vedere la [direttiva using](../../language-reference/keywords/using-directive.md).

Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi. Usare la parola chiave [namespace](../../language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

Il nome dello spazio dei nomi deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.

## <a name="namespaces-overview"></a>Panoramica degli spazi dei nomiNamespaces overview

Gli spazi dei nomi hanno le proprietà riportate di seguito:

- Consentono di organizzare progetti di codice di grandi dimensioni.
- Vengono delimitati usando l'operatore `.`.
- La direttiva `using` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.
- Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi <xref:System> di .NET.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Spazi dei nomi](~/_csharplang/spec/namespaces.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Uso degli spazi dei nomi](using-namespaces.md)
- [Come usare lo spazio dei nomi My](how-to-use-the-my-namespace.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
- [using Direttiva](../../language-reference/keywords/using-directive.md)
- [:: Operatore](../../language-reference/operators/namespace-alias-qualifier.md)
