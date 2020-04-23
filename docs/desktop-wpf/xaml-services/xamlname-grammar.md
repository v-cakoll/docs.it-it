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
# <a name="xamlname-grammar"></a><span data-ttu-id="ce6c0-102">Grammatica XamlName</span><span class="sxs-lookup"><span data-stu-id="ce6c0-102">XamlName Grammar</span></span>

<span data-ttu-id="ce6c0-103">XamlName Grammar è una grammatica specifica definita nella specifica del linguaggio XAML [MS-XAML], che viene riprodotta qui per comodità.</span><span class="sxs-lookup"><span data-stu-id="ce6c0-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="ce6c0-104">Dalla specifica XAML</span><span class="sxs-lookup"><span data-stu-id="ce6c0-104">From the XAML Specification</span></span>

<span data-ttu-id="ce6c0-105">La specifica [MS-XAML] definisce la grammatica XamlName per identificare il set di identificatori simbolici legali utilizzati per tipi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce6c0-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="ce6c0-106">I valori stringa di tipo XamlName devono essere conformi alla grammatica seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6c0-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="ce6c0-107">Che assume i seguenti valori di categoria generale come definito nel Database caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="ce6c0-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="ce6c0-108">Categoria Unicode</span><span class="sxs-lookup"><span data-stu-id="ce6c0-108">Unicode category</span></span>   | <span data-ttu-id="ce6c0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce6c0-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="ce6c0-110">LU</span><span class="sxs-lookup"><span data-stu-id="ce6c0-110">Lu</span></span>                 | <span data-ttu-id="ce6c0-111">Letter, Uppercase</span><span class="sxs-lookup"><span data-stu-id="ce6c0-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="ce6c0-112">Ll</span><span class="sxs-lookup"><span data-stu-id="ce6c0-112">Ll</span></span>                 | <span data-ttu-id="ce6c0-113">Letter, Lowercase</span><span class="sxs-lookup"><span data-stu-id="ce6c0-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="ce6c0-114">Lt</span><span class="sxs-lookup"><span data-stu-id="ce6c0-114">Lt</span></span>                 | <span data-ttu-id="ce6c0-115">Letter, Titlecase</span><span class="sxs-lookup"><span data-stu-id="ce6c0-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="ce6c0-116">Lm</span><span class="sxs-lookup"><span data-stu-id="ce6c0-116">Lm</span></span>                 | <span data-ttu-id="ce6c0-117">Letter, Modifier</span><span class="sxs-lookup"><span data-stu-id="ce6c0-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="ce6c0-118">Lo</span><span class="sxs-lookup"><span data-stu-id="ce6c0-118">Lo</span></span>                 | <span data-ttu-id="ce6c0-119">Letter, Other</span><span class="sxs-lookup"><span data-stu-id="ce6c0-119">Letter, Other</span></span>                 |
| <span data-ttu-id="ce6c0-120">Mn</span><span class="sxs-lookup"><span data-stu-id="ce6c0-120">Mn</span></span>                 | <span data-ttu-id="ce6c0-121">Contrassegno, non di spaziatura</span><span class="sxs-lookup"><span data-stu-id="ce6c0-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="ce6c0-122">Mc</span><span class="sxs-lookup"><span data-stu-id="ce6c0-122">Mc</span></span>                 | <span data-ttu-id="ce6c0-123">Mark, Spacing Combining</span><span class="sxs-lookup"><span data-stu-id="ce6c0-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="ce6c0-124">Nd</span><span class="sxs-lookup"><span data-stu-id="ce6c0-124">Nd</span></span>                 | <span data-ttu-id="ce6c0-125">Numero, Decimale</span><span class="sxs-lookup"><span data-stu-id="ce6c0-125">Number, Decimal</span></span>               |
| <span data-ttu-id="ce6c0-126">Nl</span><span class="sxs-lookup"><span data-stu-id="ce6c0-126">Nl</span></span>                 | <span data-ttu-id="ce6c0-127">Number, Letter</span><span class="sxs-lookup"><span data-stu-id="ce6c0-127">Number, Letter</span></span>                |

<span data-ttu-id="ce6c0-128">XAML definisce una seconda grammatica, DottedXamlName, usata per i riferimenti qualificati a proprietà ed eventi e anche per i membri associati.</span><span class="sxs-lookup"><span data-stu-id="ce6c0-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="ce6c0-129">Per altre informazioni, vedere Cenni preliminari <xref:System.Windows.DependencyProperty> su XAML [(WPF)](../fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ce6c0-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="ce6c0-130">I valori stringa di tipo DottedXamlName devono essere conformi alla grammatica seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6c0-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="ce6c0-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ce6c0-131">Remarks</span></span>

<span data-ttu-id="ce6c0-132">Per la specifica completa, vedere [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ce6c0-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
