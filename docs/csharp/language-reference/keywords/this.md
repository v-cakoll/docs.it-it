---
title: Parola chiave this - Riferimenti per C#
description: Parola chiave this (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715113"
---
# <a name="this-c-reference"></a>this (Riferimenti per C#)

La parola chiave `this` fa riferimento all'istanza corrente della classe e viene anche usata come modificatore del primo parametro di un metodo di estensione.

> [!NOTE]
> Questo articolo illustra l'uso di `this` con istanze della classe. Per altre informazioni sull'uso nei metodi di estensione, vedere [Metodi di estensione](../../programming-guide/classes-and-structs/extension-methods.md).

Di seguito sono riportati gli usi comuni di `this`:

- Per qualificare i membri nascosti da nomi simili, ad esempio:

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- Per passare un oggetto come parametro ad altri metodi, ad esempio:

  ```csharp
  CalcTax(this);
  ```

- Per dichiarare gli indicizzatori, ad esempio:

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

Le funzioni del membro statico, perché esistono a livello di classe e non come parte di un oggetto, non dispongono di un puntatore `this`. È un errore fare riferimento a `this` in un metodo statico.

## <a name="example"></a>Esempio

In questo esempio, `this` viene usato per qualificare i membri della classe `Employee`, `name` e `alias`, che sono nascosti da nomi simili. Viene anche usato per passare un oggetto al metodo `CalcTax`, che appartiene a un'altra classe.

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [base](base.md)
- [Metodi](../../programming-guide/classes-and-structs/methods.md)
