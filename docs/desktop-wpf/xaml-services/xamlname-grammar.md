---
title: Grammatica XamlName
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071829"
---
# <a name="xamlname-grammar"></a>Grammatica XamlName

XamlName Grammar è una grammatica specifica definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotta qui per comodità.

## <a name="from-the-xaml-specification"></a>Dalla specifica XAML

La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori simbolici legali utilizzati per tipi e proprietà.

I valori stringa di tipo XamlName devono essere conformi alla grammatica seguente:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Che assume i seguenti valori di categoria generale come definito nel Database caratteri Unicode

| Categoria Unicode   | Descrizione                   |
|--------------------|-------------------------------|
| LU                 | Letter, Uppercase             |
| Ll                 | Letter, Lowercase             |
| Lt                 | Letter, Titlecase             |
| Lm                 | Letter, Modifier              |
| Lo                 | Letter, Other                 |
| Mn                 | Contrassegno, non di spaziatura             |
| Mc                 | Mark, Spacing Combining       |
| Nd                 | Numero, Decimale               |
| Nl                 | Number, Letter                |

XAML definisce una seconda grammatica, DottedXamlName, usata per i riferimenti qualificati a proprietà ed eventi e anche per i membri associati. Per altre informazioni, vedere Cenni preliminari <xref:System.Windows.DependencyProperty> su XAML [(WPF)](../fundamentals/xaml.md).

I valori stringa di tipo DottedXamlName devono essere conformi alla grammatica seguente:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Osservazioni

Per la specifica completa, vedere [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).
