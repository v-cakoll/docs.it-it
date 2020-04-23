---
title: Estensione del markup x:Null
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071430"
---
# <a name="xnull-markup-extension"></a>Estensione del markup x:Null

Specifica `null` come valore per un membro XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Osservazioni

La parola chiave per un riferimento null è null. La parola chiave di Microsoft `Nothing`Visual Basic per `{x:Null}` un riferimento null è , ma viene sempre utilizzata come utilizzo XAML indipendentemente dal linguaggio code-behind associato al codice XAML.

L'estensione `x:Null` di markup non ha proprietà impostabili.

Un utilizzo null è spesso associato all'esposizione dei membri XAML di un valore CLR. <xref:System.Nullable%601>

L'estensione `x:Null` di markup, come tutte le`{,}`estensioni di markup XAML, usa le parentesi graffe ( ) per eseguire l'ecattività della gestione dei valori di attributo in modo che siano diversi dai valori letterali o dai riferimenti ai gestori eventi. La sintassi degli attributi è la sintassi utilizzata più di frequente con questa estensione di markup. La sintassi `<x:Null />` di un elemento oggetto è `x:Null` tecnicamente possibile, ma viene raramente utilizzata perché l'estensione di markup non ha parametri posizionali o argomenti di costruzione.

Per informazioni sulle estensioni di markup, vedere [Estensioni di markup e XAML WPF.](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

Nei servizi XAML .NET, la gestione di <xref:System.Windows.Markup.NullExtension> questa estensione di markup è definita dalla classe .

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Si `null` noti che non è necessariamente il valore di annullamento iniziale per una proprietà di dipendenza di tipo riferimento. Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su metadati specifici della proprietà. Molte proprietà di dipendenza `null` non accettano come valore, tramite markup o codice a causa delle implementazioni di callback di convalida. Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari](../../framework/wpf/advanced/dependency-properties-overview.md)sulle proprietà di dipendenza .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
