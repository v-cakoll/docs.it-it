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
ms.openlocfilehash: 32fd7b7b952ebbc853e41c0a8276d1ab487e619f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="xamlname-grammar"></a>Grammatica XamlName
Grammatica XamlName è una grammatica specifica è definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotto di seguito per praticità.  
  
## <a name="from-the-xaml-specification"></a>Dalla specifica di XAML  
 La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori simbolici validi utilizzati per i tipi e le proprietà.  
  
 I valori di tipo che XamlName deve essere conforme alla grammatica seguente stringa:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Che si presuppone che i seguenti valori di categoria generale come definito nel Database dei caratteri Unicode  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 Il codice XAML definisce una seconda grammatica, DottedXamlName, che viene utilizzato per la proprietà ed evento riferimenti completi e anche per membri associati. Per ulteriori informazioni, vedere <xref:System.Windows.DependencyProperty> e [Panoramica di XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 I valori di tipo che DottedXamlName deve essere conforme alla grammatica seguente stringa:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Note  
 Per la specifica completa, vedere [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).
