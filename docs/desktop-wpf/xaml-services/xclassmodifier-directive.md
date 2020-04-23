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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072032"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="2073c-102">Direttiva x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="2073c-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="2073c-103">Modifica il comportamento di `x:Class` compilazione XAML quando viene fornito anche.</span><span class="sxs-lookup"><span data-stu-id="2073c-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="2073c-104">In particolare, anziché `class` creare `Public` un partial con un `x:Class` livello di `NotPublic` accesso (impostazione predefinita), l'oggetto fornito viene creato con un livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="2073c-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="2073c-105">Questo comportamento influisce sul livello di accesso per la classe negli assembly generati.</span><span class="sxs-lookup"><span data-stu-id="2073c-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="2073c-106">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="2073c-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="2073c-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="2073c-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="2073c-108">*NotPublic (NotPubblico)*</span><span class="sxs-lookup"><span data-stu-id="2073c-108">*NotPublic*</span></span>|<span data-ttu-id="2073c-109">La stringa esatta da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> passare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> da specificare rispetto a varia a seconda del linguaggio di programmazione code-behind utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2073c-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="2073c-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="2073c-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="2073c-111">Dependencies</span><span class="sxs-lookup"><span data-stu-id="2073c-111">Dependencies</span></span>

<span data-ttu-id="2073c-112">[x:Class](xclass-directive.md) deve essere fornito anche sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina.x:Class must also be provided on the same element, and that element must be the root element in a page.</span><span class="sxs-lookup"><span data-stu-id="2073c-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="2073c-113">Per ulteriori informazioni, vedere [ \[Sezione MS-XAML\] 4.3.1.8.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="2073c-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="2073c-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2073c-114">Remarks</span></span>

<span data-ttu-id="2073c-115">Il valore `x:ClassModifier` di in .NET XAML Services usage varia in base al linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="2073c-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="2073c-116">La stringa da utilizzare dipende dal <xref:System.CodeDom.Compiler.CodeDomProvider> modo in cui ogni linguaggio implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>i convertitori di tipo che restituisce per definire i significati per e e se tale lingua fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2073c-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="2073c-117">Per il linguaggio C, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> la `internal`stringa da passare a designate è .</span><span class="sxs-lookup"><span data-stu-id="2073c-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="2073c-118">Per Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`stringa da passare a designate è .</span><span class="sxs-lookup"><span data-stu-id="2073c-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="2073c-119">Per c'è/CLI, non esistono destinazioni che supportano la compilazione di XAML. pertanto, il valore da passare non è specificato.</span><span class="sxs-lookup"><span data-stu-id="2073c-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="2073c-120">È anche <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> possibile`public` specificare `Public` ( in C, in Visual Basic); Tuttavia, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> la specifica viene <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> eseguita raramente perché è già il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="2073c-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="2073c-121">Altri valori con restrizioni equivalenti a livello `private` di accesso al codice `x:ClassModifier` utente, ad esempio in C, non <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> sono rilevanti perché i riferimenti alle classi annidate non sono supportati in XAML e pertanto il modificatore ha lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="2073c-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="2073c-122">Note sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="2073c-122">Security Notes</span></span>

<span data-ttu-id="2073c-123">Il livello di `x:ClassModifier` accesso dichiarato in è ancora soggetto a interpretazione da parte di particolari quadri e delle loro capacità.</span><span class="sxs-lookup"><span data-stu-id="2073c-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="2073c-124">WPFWPF include funzionalità per `x:ClassModifier` caricare `internal`e creare istanze di tipi dove è , se tale classe fa riferimento da una risorsa WPFwpf tramite un riferimento URI di tipo pack.</span><span class="sxs-lookup"><span data-stu-id="2073c-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="2073c-125">Come conseguenza di questo caso e potenzialmente altri simili implementati da `x:ClassModifier` altri framework, non si basano esclusivamente su per bloccare tutti i possibili tentativi di creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="2073c-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2073c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2073c-126">See also</span></span>

- [<span data-ttu-id="2073c-127">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="2073c-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="2073c-128">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="2073c-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="2073c-129">Direttiva x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="2073c-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="2073c-130">Sicurezza (WPF)</span><span class="sxs-lookup"><span data-stu-id="2073c-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="2073c-131">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="2073c-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
