---
title: Parola chiave namespace - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b35f0a2a5cc0b2895b491d4ee24f89955f4b8fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625800"
---
# <a name="namespace-c-reference"></a>namespace (Riferimenti per C#)

La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati. È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Osservazioni

All'interno di uno spazio dei nomi è possibile dichiarare nessuno o più di uno dei tipi elencati di seguito:

- un altro spazio dei nomi

- [Classe](class.md)

- [Interfaccia](interface.md)

- [struct](../builtin-types/struct.md)

- [Enum](../builtin-types/enum.md)

- [Delegato](../builtin-types/reference-types.md#the-delegate-type)

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

- [Informazioni di riferimento su C#](../index.md)
- [Parole chiave di C](index.md)
- [Utilizzando](using-directive.md)
- [utilizzando statica](using-static.md)
- [Qualificatore di alias dello spazio dei nomi `::`](../operators/namespace-alias-qualifier.md)
- [Spazi dei nomi](../../programming-guide/namespaces/index.md)
