---
title: Variabili di struttura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346299"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="4de7d-102">Variabili di struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4de7d-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="4de7d-103">Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di procedura e a livello di modulo come quel tipo.</span><span class="sxs-lookup"><span data-stu-id="4de7d-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="4de7d-104">Ad esempio, è possibile creare una struttura che registra le informazioni relative a un sistema di computer.</span><span class="sxs-lookup"><span data-stu-id="4de7d-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="4de7d-105">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="4de7d-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="4de7d-106">È ora possibile dichiarare variabili di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="4de7d-106">You can now declare variables of that type.</span></span> <span data-ttu-id="4de7d-107">Questa operazione viene illustrata nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="4de7d-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="4de7d-108">Nelle classi e nei moduli, le strutture dichiarate con l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) sono predefinite per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="4de7d-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="4de7d-109">Se si vuole che una struttura sia privata, assicurarsi di dichiararla usando la parola chiave [private](../../../../visual-basic/language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="4de7d-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="4de7d-110">Accesso ai valori della struttura</span><span class="sxs-lookup"><span data-stu-id="4de7d-110">Access to Structure Values</span></span>

<span data-ttu-id="4de7d-111">Per assegnare e recuperare valori dagli elementi di una variabile di struttura, è possibile utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4de7d-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="4de7d-112">Si inserisce l'operatore di accesso ai membri (`.`) tra il nome della variabile di struttura e il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4de7d-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="4de7d-113">Nell'esempio seguente viene eseguito l'accesso agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="4de7d-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="4de7d-114">Assegnazione di variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="4de7d-114">Assigning Structure Variables</span></span>

<span data-ttu-id="4de7d-115">È anche possibile assegnare una variabile a un'altra se entrambe sono dello stesso tipo di struttura.</span><span class="sxs-lookup"><span data-stu-id="4de7d-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="4de7d-116">In questo modo tutti gli elementi di una struttura vengono copiati negli elementi corrispondenti dell'altro.</span><span class="sxs-lookup"><span data-stu-id="4de7d-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="4de7d-117">Questa operazione viene illustrata nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="4de7d-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="4de7d-118">Se un elemento della struttura è un tipo di riferimento, ad esempio un `String`, `Object`o una matrice, viene copiato il puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="4de7d-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="4de7d-119">Nell'esempio precedente, se `systemInfo` aveva incluso una variabile oggetto, l'esempio precedente avrebbe copiato il puntatore da `mySystem` a `yourSystem`e una modifica ai dati dell'oggetto tramite una struttura verrebbe applicata quando si accede tramite l'altra struttura.</span><span class="sxs-lookup"><span data-stu-id="4de7d-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="4de7d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4de7d-120">See also</span></span>

- [<span data-ttu-id="4de7d-121">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4de7d-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="4de7d-122">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="4de7d-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="4de7d-123">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="4de7d-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="4de7d-124">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="4de7d-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="4de7d-125">Strutture</span><span class="sxs-lookup"><span data-stu-id="4de7d-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4de7d-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4de7d-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="4de7d-127">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="4de7d-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="4de7d-128">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="4de7d-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="4de7d-129">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="4de7d-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="4de7d-130">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="4de7d-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
