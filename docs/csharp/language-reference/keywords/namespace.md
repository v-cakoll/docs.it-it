---
title: Parola chiave namespace - Riferimenti per C#
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 04595e96f6f14b8806a2d89625151910cac9e0d2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345413"
---
# <a name="namespace-c-reference"></a>namespace (Riferimenti per C#)

La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati. È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Note

All'interno di uno spazio dei nomi è possibile dichiarare nessuno o più di uno dei tipi elencati di seguito:

- un altro spazio dei nomi

- [classe](class.md)

- [interface](interface.md)

- [struct](struct.md)

- [enum](../builtin-types/enum.md)

- [delegate](../builtin-types/reference-types.md#the-delegate-type)

Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#. Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file. Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.

Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile. Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](access-modifiers.md).

È possibile definire uno spazio dei nomi in una o più dichiarazioni. L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>Esempio

L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Spazi dei nomi](~/_csharplang/spec/namespaces.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave C#](index.md)
- [using](using-directive.md)
- [using static](using-static.md)
- [Qualificatore di alias dello spazio dei nomi `::`](../operators/namespace-alias-qualifier.md)
- [Spazi dei nomi](../../programming-guide/namespaces/index.md)
