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
# <a name="xreference-markup-extension"></a><span data-ttu-id="f432f-102">estensione di markup x:Reference</span><span class="sxs-lookup"><span data-stu-id="f432f-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="f432f-103">Fa riferimento a un'istanza dichiarata altrove nel markup XAML.</span><span class="sxs-lookup"><span data-stu-id="f432f-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="f432f-104">Il riferimento fa riferimento `x:Name`a .</span><span class="sxs-lookup"><span data-stu-id="f432f-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f432f-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="f432f-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="f432f-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="f432f-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="f432f-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="f432f-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="f432f-108">Valore `x:Name` (o valore <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>della proprietà -identified) dell'istanza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f432f-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f432f-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f432f-109">Remarks</span></span>

<span data-ttu-id="f432f-110">`x:Reference`fornisce supporto a livello di linguaggio XAML per un concetto di riferimento all'elemento che è stato altrimenti implementato in framework specifici, ad esempio WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="f432f-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="f432f-111">x:Riferimento e WPF</span><span class="sxs-lookup"><span data-stu-id="f432f-111">x:Reference and WPF</span></span>

<span data-ttu-id="f432f-112">In WPF e XAML 2006, i riferimenti agli elementi <xref:System.Windows.Data.Binding.ElementName%2A> vengono indirizzati dalla funzionalità a livello di framework dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f432f-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="f432f-113">Per la maggior parte <xref:System.Windows.Data.Binding.ElementName%2A> delle applicazioni e degli scenari WPFWPF, l'associazione deve comunque essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="f432f-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="f432f-114">Le eccezioni a queste indicazioni generali possono includere casi in cui sono presenti contesto dati o altre considerazioni sull'ambito che rendono impraticabile l'associazione dati e in cui la compilazione del markup non è coinvolta.</span><span class="sxs-lookup"><span data-stu-id="f432f-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="f432f-115">`x:Reference`è un costrutto definito in XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="f432f-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="f432f-116">In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF.</span><span class="sxs-lookup"><span data-stu-id="f432f-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="f432f-117">Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="f432f-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
