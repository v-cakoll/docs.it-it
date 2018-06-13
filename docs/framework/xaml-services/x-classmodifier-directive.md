---
title: Direttiva x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 67b53a63dbd6e1377d5684d64ed32b0374c84b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564378"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="170e8-102">Direttiva x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="170e8-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="170e8-103">Modifica il comportamento di compilazione XAML quando `x:Class` viene inoltre fornita.</span><span class="sxs-lookup"><span data-stu-id="170e8-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="170e8-104">In particolare, anziché creare un elemento parziale `class` che ha un `Public` (impostazione predefinita), livello di accesso fornito `x:Class` viene creato con un `NotPublic` livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="170e8-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="170e8-105">Questo comportamento influenza il livello di accesso per la classe nell'assembly generati.</span><span class="sxs-lookup"><span data-stu-id="170e8-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="170e8-106">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="170e8-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="170e8-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="170e8-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="170e8-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="170e8-108">*NotPublic*</span></span>|<span data-ttu-id="170e8-109">La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione codice in uso.</span><span class="sxs-lookup"><span data-stu-id="170e8-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="170e8-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="170e8-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="170e8-111">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="170e8-111">Dependencies</span></span>  
 <span data-ttu-id="170e8-112">[X:Class](../../../docs/framework/xaml-services/x-class-directive.md) necessario fornire anche sullo stesso elemento, e tale elemento deve essere l'elemento radice in una pagina.</span><span class="sxs-lookup"><span data-stu-id="170e8-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="170e8-113">Per ulteriori informazioni, vedere [ \[MS-XAML\] sezione 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="170e8-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="170e8-114">Note</span><span class="sxs-lookup"><span data-stu-id="170e8-114">Remarks</span></span>  
 <span data-ttu-id="170e8-115">Il valore di `x:ClassModifier` nei servizi XAML di .NET Framework utilizzo varia in base al linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="170e8-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="170e8-116">La stringa da utilizzare dipende dal modo in cui ogni linguaggio implementa relativo <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire il significato per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="170e8-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="170e8-117">Per c#, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.</span><span class="sxs-lookup"><span data-stu-id="170e8-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="170e8-118">Per Microsoft Visual Basic .NET, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.</span><span class="sxs-lookup"><span data-stu-id="170e8-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="170e8-119">Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nessuna destinazione esistono che supportano la compilazione di XAML; pertanto, non è specificato il valore da passare.</span><span class="sxs-lookup"><span data-stu-id="170e8-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="170e8-120">È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in c# `Public` in Visual Basic), tuttavia, specificando <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> avviene raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è già il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="170e8-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="170e8-121">Altri valori con il codice equivalente utente l'accesso a livello di restrizioni, ad esempio `private` in c#, non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e di conseguenza, il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificatore ha lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="170e8-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="170e8-122">Note sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="170e8-122">Security Notes</span></span>  
 <span data-ttu-id="170e8-123">Il livello di accesso, come dichiarato in `x:ClassModifier` viene interpretato ancora determinati Framework e le relative funzionalità.</span><span class="sxs-lookup"><span data-stu-id="170e8-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="170e8-124">WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal`, se tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento all'URI di tipo pack.</span><span class="sxs-lookup"><span data-stu-id="170e8-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="170e8-125">Di conseguenza questo caso e potenzialmente di altri utenti, quali quelle implementate da altri Framework, non fare affidamento esclusivamente su `x:ClassModifier` tenta di bloccare la creazione di istanze di tutti i possibili.</span><span class="sxs-lookup"><span data-stu-id="170e8-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170e8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="170e8-126">See Also</span></span>  
 [<span data-ttu-id="170e8-127">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="170e8-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="170e8-128">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="170e8-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="170e8-129">Direttiva x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="170e8-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [<span data-ttu-id="170e8-130">Sicurezza (WPF)</span><span class="sxs-lookup"><span data-stu-id="170e8-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="170e8-131">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="170e8-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
