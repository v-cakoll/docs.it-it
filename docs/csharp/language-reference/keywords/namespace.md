---
title: Parola chiave namespace - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b5c6b8081c188d5b184930222d54ad8f4b5d7a71
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242763"
---
# <a name="namespace-c-reference"></a>namespace (Riferimenti per C#)

La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati. È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Note

All'interno di uno spazio dei nomi è possibile dichiarare nessuno o più di uno dei tipi elencati di seguito:

- un altro spazio dei nomi

- [class](class.md)

- [interface](interface.md)

- [struct](struct.md)

- [enum](enum.md)

- [delegate](delegate.md)

Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#. Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file. Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.

Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile. Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](access-modifiers.md).

È possibile definire uno spazio dei nomi in una o più dichiarazioni. L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>Esempio

L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a>Risorse correlate

Per altre informazioni sull'uso degli spazi dei nomi, vedere gli argomenti seguenti:

- [Spazi dei nomi](../../programming-guide/namespaces/index.md)

- [Uso degli spazi dei nomi](../../programming-guide/namespaces/using-namespaces.md)

- [Procedura: Usare l'alias dello spazio dei nomi globale](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Parole chiave per gli spazi dei nomi](namespace-keywords.md)
- [using](using.md)