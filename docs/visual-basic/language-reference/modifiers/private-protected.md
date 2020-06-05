---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: b7d9f81e41950b92c787e2e50fb94fe3d7c07559
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362229"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="309da-102">Privato protetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="309da-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="309da-103">La combinazione delle parole chiave `Private Protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="309da-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="309da-104">Un `Private Protected` membro è accessibile da tutti i membri della classe che lo contiene, nonché dai tipi derivati dalla classe che lo contiene, ma solo se vengono trovati nell'assembly contenitore.</span><span class="sxs-lookup"><span data-stu-id="309da-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="309da-105">È possibile specificare `Private Protected` solo per i membri delle classi. non è possibile applicare `Private Protected` ai membri di una struttura perché le strutture non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="309da-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="309da-106">Il `Private Protected` modificatore di accesso è supportato da Visual Basic 15,5 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="309da-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="309da-107">Per usarlo, è possibile aggiungere l'elemento seguente al file del progetto di Visual Basic ( \* . vbproj).</span><span class="sxs-lookup"><span data-stu-id="309da-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="309da-108">Fino a quando nel sistema è installato Visual Basic 15,5 o versione successiva, è possibile sfruttare tutte le funzionalità del linguaggio supportate dalla versione più recente del compilatore Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="309da-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="309da-109">Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="309da-109">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="309da-110">In Visual Studio, selezionando la Guida sensibile al contesto, `private protected` viene fornita una guida per [privato](private.md) o [protetto](protected.md).</span><span class="sxs-lookup"><span data-stu-id="309da-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="309da-111">L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.</span><span class="sxs-lookup"><span data-stu-id="309da-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="309da-112">Regole</span><span class="sxs-lookup"><span data-stu-id="309da-112">Rules</span></span>

- <span data-ttu-id="309da-113">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="309da-113">**Declaration Context.**</span></span> <span data-ttu-id="309da-114">È possibile usare `Private Protected` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="309da-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="309da-115">Ciò significa che il contesto di dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="309da-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="309da-116">Comportamento</span><span class="sxs-lookup"><span data-stu-id="309da-116">Behavior</span></span>

- <span data-ttu-id="309da-117">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="309da-117">**Access Level.**</span></span> <span data-ttu-id="309da-118">Tutto il codice in una classe può accedere ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="309da-118">All code in a class can access its elements.</span></span> <span data-ttu-id="309da-119">Il codice in qualsiasi classe che deriva da una classe base e che è contenuto nello stesso assembly può accedere a tutti gli `Private Protected` elementi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="309da-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="309da-120">Tuttavia, il codice in qualsiasi classe che deriva da una classe base e che è contenuto in un assembly diverso non può accedere agli elementi della classe di base `Private Protected` .</span><span class="sxs-lookup"><span data-stu-id="309da-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="309da-121">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="309da-121">**Access Modifiers.**</span></span> <span data-ttu-id="309da-122">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="309da-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="309da-123">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="309da-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="309da-124">Il modificatore `Private Protected` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="309da-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="309da-125">[Istruzione Class](../statements/class-statement.md) di una classe annidata</span><span class="sxs-lookup"><span data-stu-id="309da-125">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="309da-126">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="309da-126">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="309da-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="309da-127">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="309da-128">[Istruzione Delegate](../statements/delegate-statement.md) di un delegato annidato in una classe</span><span class="sxs-lookup"><span data-stu-id="309da-128">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="309da-129">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="309da-129">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="309da-130">[Istruzione enum](../statements/enum-statement.md) di un'enumerazione annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="309da-130">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="309da-131">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="309da-131">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="309da-132">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="309da-132">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="309da-133">[Istruzione Interface](../statements/interface-statement.md) di un'interfaccia annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="309da-133">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="309da-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="309da-134">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="309da-135">[Istruzione Structure](../statements/structure-statement.md) di una struttura annidata in una classe</span><span class="sxs-lookup"><span data-stu-id="309da-135">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="309da-136">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="309da-136">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="309da-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="309da-137">See also</span></span>

- [<span data-ttu-id="309da-138">Pubblica</span><span class="sxs-lookup"><span data-stu-id="309da-138">Public</span></span>](public.md)
- [<span data-ttu-id="309da-139">Protetto</span><span class="sxs-lookup"><span data-stu-id="309da-139">Protected</span></span>](protected.md)
- [<span data-ttu-id="309da-140">Amico</span><span class="sxs-lookup"><span data-stu-id="309da-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="309da-141">Privata</span><span class="sxs-lookup"><span data-stu-id="309da-141">Private</span></span>](private.md)
- [<span data-ttu-id="309da-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="309da-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="309da-143">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="309da-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="309da-144">Procedure</span><span class="sxs-lookup"><span data-stu-id="309da-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="309da-145">Strutture</span><span class="sxs-lookup"><span data-stu-id="309da-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="309da-146">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="309da-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
