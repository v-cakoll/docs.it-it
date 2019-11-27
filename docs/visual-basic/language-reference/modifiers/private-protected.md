---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351350"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="c49c0-102">Privato protetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c49c0-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="c49c0-103">La combinazione delle parole chiave `Private Protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="c49c0-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c49c0-104">Un membro `Private Protected` è accessibile da tutti i membri della relativa classe che lo contiene, nonché dai tipi derivati dalla classe che lo contiene, ma solo se vengono trovati nell'assembly contenitore.</span><span class="sxs-lookup"><span data-stu-id="c49c0-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="c49c0-105">È possibile specificare `Private Protected` solo per i membri delle classi; non è possibile applicare `Private Protected` ai membri di una struttura perché le strutture non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="c49c0-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="c49c0-106">Il modificatore di accesso `Private Protected` è supportato da Visual Basic 15,5 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c49c0-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="c49c0-107">Per usarlo, è possibile aggiungere l'elemento seguente al file del progetto Visual Basic (\*. vbproj).</span><span class="sxs-lookup"><span data-stu-id="c49c0-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="c49c0-108">Fino a quando nel sistema è installato Visual Basic 15,5 o versione successiva, è possibile sfruttare tutte le funzionalità del linguaggio supportate dalla versione più recente del compilatore Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c49c0-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="c49c0-109">Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="c49c0-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c49c0-110">In Visual Studio, selezionando la Guida sensibile al contesto `private protected` viene fornita la guida per [privato](private.md) o [protetto](protected.md).</span><span class="sxs-lookup"><span data-stu-id="c49c0-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="c49c0-111">L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.</span><span class="sxs-lookup"><span data-stu-id="c49c0-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="c49c0-112">Regole</span><span class="sxs-lookup"><span data-stu-id="c49c0-112">Rules</span></span>

- <span data-ttu-id="c49c0-113">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="c49c0-113">**Declaration Context.**</span></span> <span data-ttu-id="c49c0-114">È possibile utilizzare `Private Protected` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="c49c0-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="c49c0-115">Ciò significa che il contesto di dichiarazione per un elemento di `Protected` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="c49c0-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="c49c0-116">Comportamento</span><span class="sxs-lookup"><span data-stu-id="c49c0-116">Behavior</span></span>

- <span data-ttu-id="c49c0-117">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="c49c0-117">**Access Level.**</span></span> <span data-ttu-id="c49c0-118">Tutto il codice in una classe può accedere ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="c49c0-118">All code in a class can access its elements.</span></span> <span data-ttu-id="c49c0-119">Il codice in qualsiasi classe che deriva da una classe base ed è contenuto nello stesso assembly può accedere a tutti gli elementi `Private Protected` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="c49c0-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="c49c0-120">Tuttavia, il codice in qualsiasi classe che deriva da una classe base e che è contenuto in un assembly diverso non può accedere alla classe di base `Private Protected` elementi.</span><span class="sxs-lookup"><span data-stu-id="c49c0-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="c49c0-121">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="c49c0-121">**Access Modifiers.**</span></span> <span data-ttu-id="c49c0-122">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="c49c0-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="c49c0-123">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c49c0-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="c49c0-124">Il modificatore `Private Protected` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49c0-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="c49c0-125">[Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) di una classe annidata</span><span class="sxs-lookup"><span data-stu-id="c49c0-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="c49c0-126">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="c49c0-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="c49c0-127">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="c49c0-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="c49c0-128">[Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) di un delegato annidato in una classe</span><span class="sxs-lookup"><span data-stu-id="c49c0-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="c49c0-129">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="c49c0-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="c49c0-130">[Istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md) di un'enumerazione annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="c49c0-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="c49c0-131">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="c49c0-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="c49c0-132">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="c49c0-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="c49c0-133">[Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md) di un'interfaccia annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="c49c0-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="c49c0-134">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="c49c0-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="c49c0-135">[Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) di una struttura annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="c49c0-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="c49c0-136">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="c49c0-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="c49c0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c49c0-137">See also</span></span>

- [<span data-ttu-id="c49c0-138">Public</span><span class="sxs-lookup"><span data-stu-id="c49c0-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="c49c0-139">Protected</span><span class="sxs-lookup"><span data-stu-id="c49c0-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="c49c0-140">Friend</span><span class="sxs-lookup"><span data-stu-id="c49c0-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="c49c0-141">Private</span><span class="sxs-lookup"><span data-stu-id="c49c0-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="c49c0-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="c49c0-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="c49c0-143">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c49c0-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="c49c0-144">Routine</span><span class="sxs-lookup"><span data-stu-id="c49c0-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="c49c0-145">Strutture</span><span class="sxs-lookup"><span data-stu-id="c49c0-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c49c0-146">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="c49c0-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
