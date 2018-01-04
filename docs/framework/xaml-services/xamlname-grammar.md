---
title: Grammatica XamlName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
