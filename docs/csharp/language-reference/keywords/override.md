---
title: Modificatore override - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: acad3aa3b196c184132ad1acdf52b18a799b0896
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713248"
---
# <a name="override-c-reference"></a>override (Riferimenti per C#)

Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.

## <a name="example"></a>Esempio

In questo esempio, `Square` la classe deve `GetArea` fornire `GetArea` un'implementazione `Shape` sottoposta a override di perché viene ereditata dalla classe astratta:In this example, the class must provide an overridden implementation of because is inherited from the abstract class:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base. Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override. Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`. Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md).

Non è possibile eseguire l'override di un metodo non virtuale o statico. Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.

Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`. Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](access-modifiers.md).

Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.

Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.

Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="example"></a>Esempio

Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`. La classe `SalesEmployee` include il campo aggiuntivo `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderlo in considerazione.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md)
- [Parole chiave di C#](index.md)
- [Modificatori](index.md)
- [astratto](abstract.md)
- [Virtuale](virtual.md)
- [new (modifier)](new-modifier.md)
- [Polimorfismo](../../programming-guide/classes-and-structs/polymorphism.md)
