---
title: Nomi di identificatore
description: Informazioni sulle regole per assegnare un nome valido agli identificatori nel linguaggio di programmazione C#.
ms.date: 08/21/2018
ms.openlocfilehash: bef6e2ea285b5391af3350ae42a4105d140c6d1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673368"
---
# <a name="identifier-names"></a><span data-ttu-id="e029b-103">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="e029b-103">Identifier names</span></span>

<span data-ttu-id="e029b-104">Un **identificatore** è il nome assegnato a un tipo (classe, interfaccia, struct, delegato o enumerazione), un membro, una variabile o uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e029b-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="e029b-105">Per essere validi gli identificatori devono rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="e029b-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="e029b-106">Gli identificatori devono iniziare con una lettera o con `_`.</span><span class="sxs-lookup"><span data-stu-id="e029b-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="e029b-107">Gli identificatori possono contenere caratteri alfabetici Unicode, cifre decimali, caratteri di connessione Unicode, caratteri combinati Unicode o caratteri di formattazione Unicode.</span><span class="sxs-lookup"><span data-stu-id="e029b-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="e029b-108">Per altre informazioni sulle categorie Unicode, vedere [Unicode Category Database](https://www.unicode.org/reports/tr44/) (Database categorie Unicode).</span><span class="sxs-lookup"><span data-stu-id="e029b-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="e029b-109">È possibile dichiarare gli identificatori che corrispondono a parole chiave C# usando il prefisso `@` nell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="e029b-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="e029b-110">`@` non fa parte del nome dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="e029b-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="e029b-111">Ad esempio, `@if` dichiara un identificatore denominato `if`.</span><span class="sxs-lookup"><span data-stu-id="e029b-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="e029b-112">Questi [identificatori verbatim](../../language-reference/tokens/verbatim.md) servono principalmente per garantire l'interoperabilità con gli identificatori dichiarati in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="e029b-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="e029b-113">Per una definizione completa degli identificatori validi, vedere l'[argomento sugli identificatori nelle specifiche del linguaggio C#](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span><span class="sxs-lookup"><span data-stu-id="e029b-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="e029b-114">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="e029b-114">Naming conventions</span></span>

<span data-ttu-id="e029b-115">Oltre alle regole, esiste una serie di [convenzioni di denominazione](../../../standard/design-guidelines/naming-guidelines.md) per gli identificatori, seguite in tutte le API .NET.</span><span class="sxs-lookup"><span data-stu-id="e029b-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="e029b-116">Per convenzione, i programmi C# usano `PascalCase` per nomi di tipo, spazi dei nomi e tutti i membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="e029b-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="e029b-117">Sono anche comuni le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e029b-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="e029b-118">I nomi di interfaccia iniziano con un carattere `I` maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="e029b-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="e029b-119">I tipi di attributo terminano con la parola `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="e029b-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="e029b-120">I tipi enumerazione usano un sostantivo singolare per non flag e uno plurale per flag.</span><span class="sxs-lookup"><span data-stu-id="e029b-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="e029b-121">Gli identificatori non devono contenere due caratteri `_` consecutivi.</span><span class="sxs-lookup"><span data-stu-id="e029b-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="e029b-122">Tali nomi sono riservati per gli identificatori generati dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="e029b-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e029b-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e029b-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e029b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e029b-124">See also</span></span>

- [<span data-ttu-id="e029b-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e029b-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e029b-126">Contenuto di un programma C#</span><span class="sxs-lookup"><span data-stu-id="e029b-126">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="e029b-127">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e029b-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e029b-128">Classi</span><span class="sxs-lookup"><span data-stu-id="e029b-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="e029b-129">Tipi di struttura</span><span class="sxs-lookup"><span data-stu-id="e029b-129">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="e029b-130">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="e029b-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="e029b-131">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e029b-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="e029b-132">Delegati</span><span class="sxs-lookup"><span data-stu-id="e029b-132">Delegates</span></span>](../delegates/index.md)
