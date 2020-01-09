---
title: virtual - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 47b77792fd3a2b2700ec0734851fdec534361596
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712871"
---
# <a name="virtual-c-reference"></a>virtual (Riferimenti per C#)

La parola chiave `virtual` viene usata per modificare una dichiarazione di metodo, proprietà, indicizzatore o evento e consentire che sia sottoposta a override in una classe derivata. Ad esempio, questo metodo può essere sottoposto a override da qualsiasi classe che lo eredita:

```csharp
public virtual double Area() 
{
    return x * y;
}
```

L'implementazione di un membro virtuale può essere modificata da un [membro di sostituzione](override.md) di una classe derivata. Per altre informazioni sull'uso della parola chiave `virtual`, vedere [Controllo delle versioni con le parole chiave Override e New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="remarks"></a>Note

Quando viene richiamato un metodo virtuale, il tipo di runtime dell'oggetto viene controllato per verificare la presenza di un membro di sostituzione. Viene chiamato il membro di sostituzione nella classe più derivata e potrebbe trattarsi del membro originale, se nessuna classe derivata ha eseguito l'override del membro.

Per impostazione predefinita, i metodi sono non virtuali. Non è possibile eseguire l'override di un metodo non virtuale.

Non è possibile usare il modificatore `virtual` con i modificatori `static`, `abstract`, `private` o `override`. L'esempio seguente illustra una proprietà virtuale:

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Le proprietà virtuali si comportano come i metodi virtuali, ad eccezione delle differenze nella sintassi della dichiarazione e della chiamata.

- Non è possibile usare il modificatore `virtual` su una proprietà static.

- Una proprietà virtuale ereditata può essere sottoposta a override in una classe derivata includendo una dichiarazione di proprietà che usa il modificatore `override`.

## <a name="example"></a>Esempio

In questo esempio la classe `Shape` contiene le due coordinate `x`, `y`e il metodo virtuale `Area()`. Le classi di forma diversa, ad esempio `Circle`, `Cylinder` e `Sphere`, ereditano la classe `Shape` e la superficie viene calcolata per ogni figura. Ogni classe derivata ha la propria implementazione di override di `Area()`.

Si noti che le classi ereditate `Circle`, `Sphere` e `Cylinder` usano tutte costruttori che inizializzano la classe di base, come illustrato nella seguente dichiarazione.

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

Il programma seguente calcola e visualizza l'area appropriata per ogni figura richiamando l'implementazione corretta del metodo `Area()` in base all'oggetto associato al metodo.

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Polimorfismo](../../programming-guide/classes-and-structs/polymorphism.md)
- [abstract](abstract.md)
- [override](override.md)
- [new (modifier)](new-modifier.md)
