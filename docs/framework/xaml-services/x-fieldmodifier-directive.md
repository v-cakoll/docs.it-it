---
title: Direttiva x:FieldModifier
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eccad019bf18c56c23864c7a1559ce5076d954bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="b8780-102">Direttiva x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="b8780-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="b8780-103">È possibile modificare il comportamento di compilazione XAML in modo che i campi per riferimenti a oggetti denominati definiti con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> accesso anziché il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="b8780-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b8780-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="b8780-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b8780-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="b8780-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8780-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="b8780-106">*Public*</span></span>|<span data-ttu-id="b8780-107">La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione codice che viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b8780-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="b8780-108">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="b8780-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="b8780-109">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="b8780-109">Dependencies</span></span>  
 <span data-ttu-id="b8780-110">Se viene utilizzata una produzione XAML `x:FieldModifier` in qualsiasi punto, è necessario dichiarare l'elemento radice di quella produzione XAML un [direttiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md).</span><span class="sxs-lookup"><span data-stu-id="b8780-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8780-111">Note</span><span class="sxs-lookup"><span data-stu-id="b8780-111">Remarks</span></span>  
 <span data-ttu-id="b8780-112">`x:FieldModifier` non è pertinente per dichiarare il livello di accesso generale di una classe o i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="b8780-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="b8780-113">È rilevante solo per il comportamento di elaborazione XAML quando un determinato oggetto XAML che fa parte di una produzione XAML viene elaborato e diventa un oggetto potenzialmente accessibile nell'oggetto grafico di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8780-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="b8780-114">Per impostazione predefinita, il riferimento di campo per tale oggetto è privato, che impedisce ai consumer dei controlli di modifica diretta di un oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="b8780-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="b8780-115">Al contrario, i consumer di controllo dovrebbero modificare l'oggetto grafico utilizzando i modelli standard che sono abilitati per i modelli di programmazione, ad esempio ottenendo la radice di layout, l'elemento figlio, le raccolte di elementi, le proprietà pubbliche dedicate, e così via.</span><span class="sxs-lookup"><span data-stu-id="b8780-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="b8780-116">Il valore per il `x:FieldModifier` attributo varia in base al linguaggio di programmazione e il suo scopo può variare in Framework specifici.</span><span class="sxs-lookup"><span data-stu-id="b8780-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="b8780-117">La stringa da utilizzare dipende dal modo in cui ogni linguaggio implementa relativo <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire il significato per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b8780-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="b8780-118">Per c#, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `public`.</span><span class="sxs-lookup"><span data-stu-id="b8780-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
-   <span data-ttu-id="b8780-119">Per Microsoft Visual Basic .NET, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `Public`.</span><span class="sxs-lookup"><span data-stu-id="b8780-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
-   <span data-ttu-id="b8780-120">Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nessuna destinazione disponibile per il codice XAML attualmente esistono, pertanto non è definita la stringa da passare.</span><span class="sxs-lookup"><span data-stu-id="b8780-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="b8780-121">È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in c# `Friend` in Visual Basic) ma la specifica <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> insolito perché `NotPublic` il comportamento è già il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b8780-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="b8780-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è il comportamento predefinito in quanto è insolito che codice all'esterno dell'assembly compilato il codice XAML deve accedere a un elemento creato XAML.</span><span class="sxs-lookup"><span data-stu-id="b8780-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="b8780-123">Architettura di sicurezza WPF con il comportamento di compilazione XAML non vengono dichiarati i campi che memorizzano le istanze dell'elemento come pubblici, a meno che non si imposti il `x:FieldModifier` per consentire l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="b8780-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="b8780-124">`x:FieldModifier` è importante solo per gli elementi con un [direttiva X:Name](../../../docs/framework/xaml-services/x-name-directive.md) perché tale nome viene utilizzato per fare riferimento al campo dopo che è pubblico.</span><span class="sxs-lookup"><span data-stu-id="b8780-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="b8780-125">Per impostazione predefinita, la classe parziale per l'elemento radice è pubblica. Tuttavia, è possibile renderlo non pubblici tramite il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span><span class="sxs-lookup"><span data-stu-id="b8780-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span> <span data-ttu-id="b8780-126">Il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md) interesserà anche il livello di accesso dell'istanza di classe dell'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="b8780-126">The [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="b8780-127">È possibile inserire `x:Name` e `x:FieldModifier` nella radice solo elemento, ma questo crea una copia di campo pubblico dell'elemento radice, con il livello vero elemento radice classe accesso ancora controllata da [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span><span class="sxs-lookup"><span data-stu-id="b8780-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8780-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8780-128">See Also</span></span>  
 [<span data-ttu-id="b8780-129">Classi XAML e personalizzate per WPF</span><span class="sxs-lookup"><span data-stu-id="b8780-129">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="b8780-130">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="b8780-130">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="b8780-131">Direttiva x:Name</span><span class="sxs-lookup"><span data-stu-id="b8780-131">x:Name Directive</span></span>](../../../docs/framework/xaml-services/x-name-directive.md)  
 [<span data-ttu-id="b8780-132">Compilazione di un'applicazione WPF (WPF)</span><span class="sxs-lookup"><span data-stu-id="b8780-132">Building a WPF Application (WPF)</span></span>](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="b8780-133">Direttiva x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="b8780-133">x:ClassModifier Directive</span></span>](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
