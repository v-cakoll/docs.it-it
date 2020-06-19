---
title: -Nullable (opzioni del compilatore C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 7454bb316507c3aaea208094127552712421dff6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990122"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="3e1b1-102">-Nullable (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="3e1b1-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="3e1b1-103">L'opzione **-Nullable** consente di specificare il contesto Nullable desiderato.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e1b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e1b1-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="3e1b1-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3e1b1-105">Arguments</span></span>

<span data-ttu-id="3e1b1-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3e1b1-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="3e1b1-107">Se `+` si specifica, o semplicemente **Nullable**, il compilatore Abilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="3e1b1-108">`-`Se si specifica, che è attivo se non si specifica **-Nullable**, Disabilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="3e1b1-109">`enable`&#124; `disable` &#124; `warnings` &#124;`annotations`</span><span class="sxs-lookup"><span data-stu-id="3e1b1-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="3e1b1-110">Specifica l'opzione di contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-110">Specifies the nullable context option.</span></span> <span data-ttu-id="3e1b1-111">Simile a `+` o `-` , per abilitare e disabilitare, ma consente una maggiore granularità della specificità del contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="3e1b1-112">L' `enable` argomento, che è attivo come se si specifica **-Nullable**, Abilita il contesto Nullable.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="3e1b1-113">Se `disable` si specifica, il contesto nullable viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="3e1b1-114">Quando si specifica l' `warnings` argomento, **-Nullable: Warnings**, il contesto di avviso Nullable è abilitato.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="3e1b1-115">Quando si specifica l' `annotations` argomento **Nullable: Annotations**, il contesto dell'annotazione Nullable è abilitato.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e1b1-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3e1b1-116">Remarks</span></span>

<span data-ttu-id="3e1b1-117">L'analisi del flusso viene utilizzata per dedurre il supporto dei valori Null delle variabili all'interno del codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="3e1b1-118">Il supporto di valori null derivati di una variabile è indipendente dal supporto di valori null dichiarato della variabile.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="3e1b1-119">Le chiamate al metodo vengono analizzate anche quando vengono omesse in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="3e1b1-120">Ad esempio, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in modalità di rilascio.</span><span class="sxs-lookup"><span data-stu-id="3e1b1-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="3e1b1-121">La chiamata dei metodi annotati con gli attributi seguenti influirà anche sull'analisi del flusso:</span><span class="sxs-lookup"><span data-stu-id="3e1b1-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="3e1b1-122">Condizioni preliminari semplici: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="3e1b1-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="3e1b1-123">Semplici post-condizioni: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="3e1b1-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="3e1b1-124">Condizioni postali condizionali: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="3e1b1-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="3e1b1-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(ad esempio, `DoesNotReturnIf(false)` per <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ) e<xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="3e1b1-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="3e1b1-126">Post-condizioni del membro: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> e<xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="3e1b1-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="3e1b1-127">Per impostare questa opzione del compilatore in un progetto</span><span class="sxs-lookup"><span data-stu-id="3e1b1-127">To set this compiler option in a project</span></span>

<span data-ttu-id="3e1b1-128">Modificare il file con *estensione csproj* per aggiungere il `<Nullable>` tag all'interno di una `Project/PropertyGroup` gerarchia:</span><span class="sxs-lookup"><span data-stu-id="3e1b1-128">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="3e1b1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e1b1-129">See also</span></span>

- [<span data-ttu-id="3e1b1-130">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="3e1b1-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3e1b1-131">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="3e1b1-131">Nullable reference types</span></span>](../../nullable-references.md)
