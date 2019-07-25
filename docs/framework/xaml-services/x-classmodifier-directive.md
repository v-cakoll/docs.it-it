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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484753"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="54f98-102">Direttiva x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="54f98-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="54f98-103">Modifica il comportamento di compilazione `x:Class` XAML quando viene fornito anche.</span><span class="sxs-lookup"><span data-stu-id="54f98-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="54f98-104">In particolare, anziché creare un oggetto `class` parziale `Public` con livello di accesso (impostazione predefinita), l'oggetto `x:Class` fornito viene creato con `NotPublic` un livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="54f98-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="54f98-105">Questo comportamento influiscono sul livello di accesso per la classe negli assembly generati.</span><span class="sxs-lookup"><span data-stu-id="54f98-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="54f98-106">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="54f98-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="54f98-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="54f98-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54f98-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="54f98-108">*NotPublic*</span></span>|<span data-ttu-id="54f98-109">La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e varia a seconda del linguaggio di programmazione code-behind usato.</span><span class="sxs-lookup"><span data-stu-id="54f98-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="54f98-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="54f98-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="54f98-111">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="54f98-111">Dependencies</span></span>  
 <span data-ttu-id="54f98-112">è necessario fornire anche [x:Class](x-class-directive.md) sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina.</span><span class="sxs-lookup"><span data-stu-id="54f98-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="54f98-113">Per ulteriori informazioni, vedere [ \[la sezione MS\] -XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="54f98-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f98-114">Note</span><span class="sxs-lookup"><span data-stu-id="54f98-114">Remarks</span></span>  
 <span data-ttu-id="54f98-115">Il valore di `x:ClassModifier` in .NET Framework uso dei servizi XAML varia in base al linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="54f98-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="54f98-116">La stringa da usare dipende dal modo in cui ogni linguaggio implementa <xref:System.CodeDom.Compiler.CodeDomProvider> i convertitori di tipi che restituisce per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>e se tale lingua fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="54f98-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="54f98-117">Per C#, la stringa da passare a designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.</span><span class="sxs-lookup"><span data-stu-id="54f98-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="54f98-118">Per Microsoft Visual Basic .NET, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.</span><span class="sxs-lookup"><span data-stu-id="54f98-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="54f98-119">Per C++/CLI non esistono destinazioni che supportano la compilazione di XAML. Pertanto, il valore da passare non è specificato.</span><span class="sxs-lookup"><span data-stu-id="54f98-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="54f98-120">È anche possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic). Tuttavia, l' <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> impostazione di viene eseguita raramente <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> perché è già il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="54f98-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="54f98-121">Altri valori con restrizioni a livello di accesso del codice utente equivalente, `private` ad C#esempio in, non sono `x:ClassModifier` rilevanti per perché i riferimenti a classi annidate non sono supportati in XAML <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e pertanto il modificatore ha lo stesso effetto .</span><span class="sxs-lookup"><span data-stu-id="54f98-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="54f98-122">Note sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="54f98-122">Security Notes</span></span>  
 <span data-ttu-id="54f98-123">Il livello di accesso dichiarato in `x:ClassModifier` è ancora soggetto all'interpretazione da parte di framework specifici e alle relative funzionalità.</span><span class="sxs-lookup"><span data-stu-id="54f98-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="54f98-124">WPF include funzionalità per caricare e creare istanze di tipi `x:ClassModifier` in `internal`cui è, se a tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack.</span><span class="sxs-lookup"><span data-stu-id="54f98-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="54f98-125">Come conseguenza di questo caso e potenzialmente altri come implementati da altri Framework, non si basano esclusivamente su `x:ClassModifier` per bloccare tutti i possibili tentativi di creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="54f98-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f98-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f98-126">See also</span></span>

- [<span data-ttu-id="54f98-127">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="54f98-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="54f98-128">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="54f98-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="54f98-129">Direttiva x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="54f98-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="54f98-130">Sicurezza (WPF)</span><span class="sxs-lookup"><span data-stu-id="54f98-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="54f98-131">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="54f98-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
