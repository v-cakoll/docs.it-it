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
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031597"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="04385-102">Grammatica XamlName</span><span class="sxs-lookup"><span data-stu-id="04385-102">XamlName Grammar</span></span>
<span data-ttu-id="04385-103">Grammatica XamlName è una grammatica specifica che viene definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotto di seguito per praticità.</span><span class="sxs-lookup"><span data-stu-id="04385-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="04385-104">Dalla specifica di XAML</span><span class="sxs-lookup"><span data-stu-id="04385-104">From the XAML Specification</span></span>  
 <span data-ttu-id="04385-105">La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori validi sui simboli utilizzati per i tipi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="04385-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="04385-106">I valori di tipo che nomexaml deve essere conforme alla grammatica seguente stringa:</span><span class="sxs-lookup"><span data-stu-id="04385-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="04385-107">Che si presuppone che i seguenti valori di categoria generale come definito nel Database di caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="04385-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="04385-108">XAML definisce una grammatica di secondo, DottedXamlName, che viene usato per la proprietà ed evento riferimenti completi e anche per membri associati.</span><span class="sxs-lookup"><span data-stu-id="04385-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="04385-109">Per altre informazioni, vedere <xref:System.Windows.DependencyProperty> e [Cenni preliminari su XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="04385-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="04385-110">I valori di tipo che DottedXamlName deve essere conforme alla grammatica seguente stringa:</span><span class="sxs-lookup"><span data-stu-id="04385-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="04385-111">Note</span><span class="sxs-lookup"><span data-stu-id="04385-111">Remarks</span></span>  
 <span data-ttu-id="04385-112">Per la specifica completa, vedere [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="04385-112">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
