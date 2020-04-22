---
title: 'Dichiarazioni di importazione: parola chiave open'
description: Informazioni sulle dichiarazioni di importazione di F e su come specificano un modulo o uno spazio dei nomi a cui è possibile fare riferimento gli elementi senza usare un nome completo.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021538"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="de43f-103">Dichiarazioni di importazione: parola chiave `open`</span><span class="sxs-lookup"><span data-stu-id="de43f-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="de43f-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="de43f-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="de43f-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="de43f-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="de43f-106">Una *dichiarazione* di importazione specifica un modulo o uno spazio dei nomi i cui elementi possono fare riferimento senza utilizzare un nome completo.</span><span class="sxs-lookup"><span data-stu-id="de43f-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="de43f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de43f-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="de43f-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="de43f-108">Remarks</span></span>

<span data-ttu-id="de43f-109">Il riferimento al codice tramite lo spazio dei nomi completo o il percorso del modulo ogni volta può creare codice difficile da scrivere, leggere e gestire.</span><span class="sxs-lookup"><span data-stu-id="de43f-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="de43f-110">In alternativa, è `open` possibile utilizzare la parola chiave per i moduli e gli spazi dei nomi utilizzati di frequente in modo che quando si fa riferimento a un membro di tale modulo o spazio dei nomi, è possibile utilizzare la forma breve del nome anziché il nome completo.</span><span class="sxs-lookup"><span data-stu-id="de43f-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="de43f-111">Questa parola chiave `using` è simile alla `using namespace` parola chiave in `Imports` C, in Visual C</span><span class="sxs-lookup"><span data-stu-id="de43f-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="de43f-112">Il modulo o lo spazio dei nomi fornito deve trovarsi nello stesso progetto o in un progetto o un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="de43f-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="de43f-113">In caso contrario, è possibile aggiungere un riferimento `-reference` al progetto o utilizzare l'opzione della riga di comando (o la relativa abbreviazione, `-r`).</span><span class="sxs-lookup"><span data-stu-id="de43f-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="de43f-114">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="de43f-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="de43f-115">La dichiarazione di importazione rende disponibili i nomi nel codice che segue la dichiarazione, fino alla fine dello spazio dei nomi, del modulo o del file che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="de43f-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="de43f-116">Quando si utilizzano più dichiarazioni di importazione, queste devono essere visualizzate su righe separate.</span><span class="sxs-lookup"><span data-stu-id="de43f-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="de43f-117">Nel codice seguente viene `open` illustrato l'utilizzo della parola chiave per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="de43f-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="de43f-118">Quando si verificano ambiguità quando si verifica lo stesso nome in più di un modulo o spazio dei nomi aperto, il compilatore F non genera un errore o un avviso.</span><span class="sxs-lookup"><span data-stu-id="de43f-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="de43f-119">Quando si verificano ambiguità, F , fornisce la preferenza al modulo o allo spazio dei nomi aperto più di recente.</span><span class="sxs-lookup"><span data-stu-id="de43f-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="de43f-120">Nel codice seguente, ad `empty` `Seq.empty`esempio, `empty` si intende , `List` `Seq` anche se si trova in entrambi i moduli e .</span><span class="sxs-lookup"><span data-stu-id="de43f-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="de43f-121">Pertanto, prestare attenzione quando si `List` aprono moduli o spazi dei nomi, ad esempio o `Seq` che contengono membri con nomi identici. invece, prendere in considerazione l'utilizzo dei nomi completi.</span><span class="sxs-lookup"><span data-stu-id="de43f-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="de43f-122">È consigliabile evitare qualsiasi situazione in cui il codice dipende dall'ordine delle dichiarazioni di importazione.</span><span class="sxs-lookup"><span data-stu-id="de43f-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="de43f-123">Spazi dei nomi aperti per impostazione predefinitaNamespaces That Are Open by Default</span><span class="sxs-lookup"><span data-stu-id="de43f-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="de43f-124">Alcuni spazi dei nomi vengono usati così di frequente nel codice F , che vengono aperti in modo implicito senza la necessità di una dichiarazione di importazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="de43f-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="de43f-125">Nella tabella seguente vengono illustrati gli spazi dei nomi aperti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="de43f-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="de43f-126">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="de43f-126">Namespace</span></span>|<span data-ttu-id="de43f-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de43f-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="de43f-128">Contiene le definizioni di base dei `int` tipi `float`F , per i tipi incorporati, ad esempio e .</span><span class="sxs-lookup"><span data-stu-id="de43f-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="de43f-129">Contiene operazioni aritmetiche `+` `*`di base come e .</span><span class="sxs-lookup"><span data-stu-id="de43f-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="de43f-130">Contiene classi di raccolte non `List` `Array`modificabili, ad esempio e .</span><span class="sxs-lookup"><span data-stu-id="de43f-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="de43f-131">Contiene i tipi per i costrutti di controllo, ad esempio la valutazione lazy e i flussi di lavoro asincroni.</span><span class="sxs-lookup"><span data-stu-id="de43f-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="de43f-132">Contiene funzioni per l'I/O `printf` formattato, ad esempio la funzione.</span><span class="sxs-lookup"><span data-stu-id="de43f-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="de43f-133">Attributo AutoOpen</span><span class="sxs-lookup"><span data-stu-id="de43f-133">AutoOpen Attribute</span></span>

<span data-ttu-id="de43f-134">È possibile `AutoOpen` applicare l'attributo a un assembly se si desidera aprire automaticamente uno spazio dei nomi o un modulo quando si fa riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="de43f-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="de43f-135">È inoltre possibile `AutoOpen` applicare l'attributo a un modulo per aprire automaticamente tale modulo quando viene aperto il modulo padre o lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="de43f-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="de43f-136">Per ulteriori informazioni, vedere [Classe Core.AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="de43f-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="de43f-137">Attributo RequireQualifiedAccess</span><span class="sxs-lookup"><span data-stu-id="de43f-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="de43f-138">Alcuni moduli, record o tipi `RequireQualifiedAccess` di unione possono specificare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="de43f-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="de43f-139">Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto che si includa una dichiarazione di importazione.</span><span class="sxs-lookup"><span data-stu-id="de43f-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="de43f-140">Se si utilizza questo attributo in modo strategico nei tipi che definiscono i nomi di uso comune, è possibile evitare conflitti di nomi e quindi rendere il codice più resiliente alle modifiche nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="de43f-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="de43f-141">Per ulteriori informazioni, vedere [Classe Core.RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="de43f-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="de43f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de43f-142">See also</span></span>

- [<span data-ttu-id="de43f-143">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="de43f-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="de43f-144">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="de43f-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="de43f-145">Moduli</span><span class="sxs-lookup"><span data-stu-id="de43f-145">Modules</span></span>](modules.md)
