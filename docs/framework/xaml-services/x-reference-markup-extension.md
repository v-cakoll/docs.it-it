---
title: estensione di markup x:Reference
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03b63cb40e57223d5c66c03fb60780689cd6c925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="2039e-102">estensione di markup x:Reference</span><span class="sxs-lookup"><span data-stu-id="2039e-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="2039e-103">Fa riferimento a un'istanza che è dichiarata in un' posizione nel markup XAML.</span><span class="sxs-lookup"><span data-stu-id="2039e-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="2039e-104">Il riferimento si riferisce a un elemento `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="2039e-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2039e-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="2039e-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="2039e-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="2039e-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2039e-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="2039e-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="2039e-108">Il `x:Name` valore (o valore del <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-proprietà identificata) dell'istanza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2039e-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2039e-109">Note</span><span class="sxs-lookup"><span data-stu-id="2039e-109">Remarks</span></span>  
 <span data-ttu-id="2039e-110">`x:Reference`fornisce supporto a livello di linguaggio XAML per un concetto di riferimento di elemento che è stato implementato in caso contrario in Framework specifici, ad esempio WPF.</span><span class="sxs-lookup"><span data-stu-id="2039e-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="2039e-111">X:Reference e WPF</span><span class="sxs-lookup"><span data-stu-id="2039e-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="2039e-112">In WPF e XAML 2006, i riferimenti dell'elemento vengono indirizzati mediante la funzionalità a livello di framework di <xref:System.Windows.Data.Binding.ElementName%2A> associazione.</span><span class="sxs-lookup"><span data-stu-id="2039e-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="2039e-113">Per la maggior parte delle applicazioni WPF e scenari, <xref:System.Windows.Data.Binding.ElementName%2A> deve ancora essere utilizzata l'associazione.</span><span class="sxs-lookup"><span data-stu-id="2039e-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="2039e-114">Eccezioni a questa Guida generale potrebbero includere casi in cui sono presenti contesto dei dati o altre considerazioni di ambito che causa è consigliabile eseguire l'associazione dati e la compilazione del markup non è coinvolto.</span><span class="sxs-lookup"><span data-stu-id="2039e-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="2039e-115">`x:Reference`è un costrutto definito in XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="2039e-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="2039e-116">In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF.</span><span class="sxs-lookup"><span data-stu-id="2039e-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="2039e-117">Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="2039e-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
