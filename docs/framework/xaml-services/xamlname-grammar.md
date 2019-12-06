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
ms.openlocfilehash: a1e7a5a03db4a24ed4d13d62899754cfe9e76b56
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837155"
---
# <a name="xamlname-grammar"></a>Grammatica XamlName
XamlName grammatica è una grammatica specifica definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotta qui per praticità.  
  
## <a name="from-the-xaml-specification"></a>Dalla specifica XAML  
 La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori simbolici validi utilizzati per i tipi e le proprietà.  
  
 I valori stringa di tipo XamlName devono essere conformi alla grammatica seguente:  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Che presuppone i seguenti valori di categoria generali definiti nel database di caratteri Unicode  

| Categoria Unicode   | Descrizione                   |
|--------------------|-------------------------------|
| Lu                 | Letter, Uppercase             |
| Ll                 | Letter, Lowercase             |
| Lt                 | Letter, Titlecase             |
| Lm                 | Letter, Modifier              |
| Lo                 | Letter, Other                 |
| Mn                 | Contrassegno, non spaziatura             |
| Mc                 | Mark, Spacing Combining       |
| Nd                 | Numero, decimale               |
| Nl                 | Number, Letter                |
 
 XAML definisce una seconda grammatica, DottedXamlName, usata per i riferimenti a proprietà ed eventi e per i membri associati. Per ulteriori informazioni, vedere <xref:System.Windows.DependencyProperty> e [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).  
  
 I valori stringa di tipo DottedXamlName devono essere conformi alla grammatica seguente:  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Note  
 Per la specifica completa, vedere [\[\]MS-XAML ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).
