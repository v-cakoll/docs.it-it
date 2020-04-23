---
title: Estensione del markup x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072046"
---
# <a name="xarray-markup-extension"></a>Estensione del markup x:Array

Fornisce supporto generale per matrici di oggetti in XAML tramite un'estensione di markup. Corrisponde al `x:ArrayExtension` tipo XAML in [MS-XAML].

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`typeName`|Nome del tipo che `x:Array` il tipo conterrà. `typeName`può essere (e spesso è) prefisso per uno spazio dei nomi XAML che contiene le definizioni di tipo XAML.|
|`arrayContents`|Contenuto degli elementi assegnato alla `ArrayExtension.Items` proprietà intrinseca. In genere, questi elementi vengono specificati come `x:Array` uno o più elementi oggetto contenuti all'interno dei tag di apertura e chiusura. Gli oggetti specificati qui devono essere assegnabili `typeName`al tipo XAML specificato in .|

## <a name="remarks"></a>Osservazioni

`Type`è un attributo `x:Array` obbligatorio per tutti gli elementi oggetto. Non `Type` è necessario che un `x:Type` valore di parametro utilizzi un'estensione di markup. il nome breve del tipo è un tipo XAML, che può essere specificato come stringa.

Nell'implementazione dei servizi XAML .NET, la relazione <xref:System.Type> tra il tipo XAML di input e CLR di output della matrice creata è influenzata dal contesto del servizio per le estensioni di markup. L'output <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> è il del tipo XAML di <xref:System.Xaml.XamlType> input, dopo aver <xref:System.Windows.Markup.IXamlTypeResolver> cercato il necessario in base al contesto dello schema XAML e al servizio fornito dal contesto.

Durante l'elaborazione, il `ArrayExtension.Items` contenuto della matrice viene assegnato alla proprietà intrinseca. Nell'implementazione, <xref:System.Windows.Markup.ArrayExtension> questo <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>è rappresentato da .

Nell'implementazione dei servizi XAML .NET, la <xref:System.Windows.Markup.ArrayExtension> gestione di questa estensione di markup è definita dalla classe . <xref:System.Windows.Markup.ArrayExtension>non è sealed e può essere utilizzato come base per un'implementazione dell'estensione di markup per un tipo di matrice personalizzato.

`x:Array`è più destinato all'estensibilità generale del linguaggio in XAML. Ma `x:Array` può anche essere utile per specificare i valori XAML di determinate proprietà che accettano raccolte supportate da XAML come contenuto della proprietà strutturata. Ad esempio, è possibile specificare il contenuto di una <xref:System.Collections.IEnumerable> proprietà con un `x:Array` utilizzo.

`x:Array` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. `x:Array`è parzialmente un'eccezione a tale regola `x:Array` perché invece di fornire una gestione alternativa del valore dell'attributo, fornisce una gestione alternativa del relativo contenuto di testo interno. Questo comportamento consente ai tipi che potrebbero non essere supportati da un modello di contenuto esistente di essere raggruppati in una matrice e di fare riferimento in un secondo momento nel code-behind accedendo alla matrice denominata. è possibile <xref:System.Array> chiamare i metodi per ottenere singoli elementi della matrice.

Tutte le estensioni di markup{,} `)` in XAML usano le parentesi graffe (nella sintassi degli attributi, che è la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve elaborare il valore dell'attributo. Per altre informazioni sulle estensioni di markup in generale, vedere Convertitori di tipi ed estensioni di [markup per XAML.](type-converters-and-markup-extensions.md)

In XAML 2009, `x:Array` è definito come una primitiva del linguaggio anziché un'estensione di markup. Per ulteriori informazioni, vedere [Tipi incorporati per le primitive](types-for-primitives.md)di linguaggio XAML comuni .

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

In genere, gli elementi `x:Array` oggetto che popolano un non sono elementi presenti nello spazio dei nomi [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML e richiedono un mapping del prefisso a uno spazio dei nomi XAML non predefinito.

Ad esempio, di seguito è riportata una `sys` semplice matrice `x`di due stringhe, con il prefisso (e anche ) definito a livello della matrice.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

Per i tipi personalizzati utilizzati come elementi della matrice, la classe deve supportare anche i requisiti per la cui istanziare in XAML viene creata un'istanza in XAML come elementi oggetto. Per altre informazioni, vedere [XAML e classi personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

## <a name="see-also"></a>Vedere anche

- [Estensioni di markup e XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Tipi migrati da WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
