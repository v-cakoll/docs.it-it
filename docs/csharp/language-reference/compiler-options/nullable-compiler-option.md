---
title: -Nullable (opzioni del compilatore C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449813"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="c1705-102">-Nullable (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="c1705-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="c1705-103">L'opzione **-Nullable** consente di specificare il contesto Nullable desiderato.</span><span class="sxs-lookup"><span data-stu-id="c1705-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1705-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1705-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="c1705-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c1705-105">Arguments</span></span>

<span data-ttu-id="c1705-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c1705-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="c1705-107">Se `+` si specifica, o semplicemente **Nullable**, il compilatore Abilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="c1705-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="c1705-108">`-`Se si specifica, che è attivo se non si specifica **-Nullable**, Disabilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="c1705-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="c1705-109">`enable`&#124; `disable` &#124; `warnings` &#124;`annotations`</span><span class="sxs-lookup"><span data-stu-id="c1705-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="c1705-110">Specifica l'opzione di contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="c1705-110">Specifies the nullable context option.</span></span> <span data-ttu-id="c1705-111">Simile a `+` o `-` , per abilitare e disabilitare, ma consente una maggiore granularità della specificità del contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="c1705-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="c1705-112">L' `enable` argomento, che è attivo come se si specifica **-Nullable**, Abilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="c1705-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="c1705-113">Se `disable` si specifica, il contesto nullable viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c1705-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="c1705-114">Quando si specifica l' `warnings` argomento, **-Nullable: Warnings**, il contesto di avviso Nullable è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c1705-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="c1705-115">Quando si specifica l' `annotations` argomento **Nullable: Annotations**, il contesto dell'annotazione Nullable è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c1705-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1705-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1705-116">Remarks</span></span>

<span data-ttu-id="c1705-117">L'analisi del flusso viene utilizzata per dedurre il supporto dei valori Null delle variabili all'interno del codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c1705-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="c1705-118">Il supporto di valori null derivati di una variabile è indipendente dal supporto di valori null dichiarato della variabile.</span><span class="sxs-lookup"><span data-stu-id="c1705-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="c1705-119">Le chiamate al metodo vengono analizzate anche quando vengono omesse in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="c1705-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="c1705-120">Ad esempio, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in modalità di rilascio.</span><span class="sxs-lookup"><span data-stu-id="c1705-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="c1705-121">La chiamata dei metodi annotati con gli attributi seguenti influirà anche sull'analisi del flusso:</span><span class="sxs-lookup"><span data-stu-id="c1705-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="c1705-122">Condizioni preliminari semplici: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="c1705-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="c1705-123">Semplici post-condizioni: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="c1705-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="c1705-124">Condizioni postali condizionali: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="c1705-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="c1705-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(ad esempio `DoesNotReturnIf(false)` per <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ) e<xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="c1705-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (e.g. `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="c1705-126">Post-condizioni del membro: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> e<xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="c1705-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="c1705-127">Per impostare questa opzione del compilatore in un progetto</span><span class="sxs-lookup"><span data-stu-id="c1705-127">To set this compiler option in a project</span></span>

<span data-ttu-id="c1705-128">Modificare il *. csproj* per aggiungere il `<Nullable>` tag all'interno di una `Project/PropertyGroup` gerarchia:</span><span class="sxs-lookup"><span data-stu-id="c1705-128">Edit the *.csproj* to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="c1705-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1705-129">See also</span></span>

- [<span data-ttu-id="c1705-130">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="c1705-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c1705-131">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="c1705-131">Nullable reference types</span></span>](../../nullable-references.md)
