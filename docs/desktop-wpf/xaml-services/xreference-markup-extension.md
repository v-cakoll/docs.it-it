---
title: estensione di markup x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071381"
---
# <a name="xreference-markup-extension"></a>estensione di markup x:Reference

Fa riferimento a un'istanza dichiarata altrove nel markup XAML. Il riferimento fa riferimento `x:Name`a .

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`instancexName`|Valore `x:Name` (o valore <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>della proprietà -identified) dell'istanza di riferimento.|

## <a name="remarks"></a>Osservazioni

`x:Reference`fornisce supporto a livello di linguaggio XAML per un concetto di riferimento all'elemento che è stato altrimenti implementato in framework specifici, ad esempio WPFWPF.

## <a name="xreference-and-wpf"></a>x:Riferimento e WPF

In WPF e XAML 2006, i riferimenti agli elementi <xref:System.Windows.Data.Binding.ElementName%2A> vengono indirizzati dalla funzionalità a livello di framework dell'associazione. Per la maggior parte <xref:System.Windows.Data.Binding.ElementName%2A> delle applicazioni e degli scenari WPFWPF, l'associazione deve comunque essere utilizzata. Le eccezioni a queste indicazioni generali possono includere casi in cui sono presenti contesto dati o altre considerazioni sull'ambito che rendono impraticabile l'associazione dati e in cui la compilazione del markup non è coinvolta.

`x:Reference`è un costrutto definito in XAML 2009. In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF. Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.
