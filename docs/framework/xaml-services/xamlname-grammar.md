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
ms.openlocfilehash: 2a934316517047da6b6aec8e88026024b9a25f65
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514801"
---
# <a name="xamlname-grammar"></a>Grammatica XamlName
Grammatica XamlName è una grammatica specifica che viene definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotto di seguito per praticità.  
  
## <a name="from-the-xaml-specification"></a>Dalla specifica di XAML  
 La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori validi sui simboli utilizzati per i tipi e proprietà.  
  
 I valori di tipo che nomexaml deve essere conforme alla grammatica seguente stringa:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Che si presuppone che i seguenti valori di categoria generale come definito nel Database di caratteri Unicode  
  
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
  
 XAML definisce una grammatica di secondo, DottedXamlName, che viene usato per la proprietà ed evento riferimenti completi e anche per membri associati. Per altre informazioni, vedere <xref:System.Windows.DependencyProperty> e [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 I valori di tipo che DottedXamlName deve essere conforme alla grammatica seguente stringa:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Note  
 Per la specifica completa, vedere [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).
