---
title: Variabili di struttura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393585"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="f8576-102">Variabili di struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8576-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="f8576-103">Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di procedura e a livello di modulo come quel tipo.</span><span class="sxs-lookup"><span data-stu-id="f8576-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="f8576-104">Ad esempio, è possibile creare una struttura che registra le informazioni relative a un sistema di computer.</span><span class="sxs-lookup"><span data-stu-id="f8576-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="f8576-105">L'esempio seguente illustra questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f8576-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="f8576-106">È ora possibile dichiarare variabili di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="f8576-106">You can now declare variables of that type.</span></span> <span data-ttu-id="f8576-107">Questa operazione viene illustrata nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="f8576-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="f8576-108">Nelle classi e nei moduli, le strutture dichiarate con l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) sono predefinite per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="f8576-108">In classes and modules, structures declared using the [Dim Statement](../../../language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="f8576-109">Se si vuole che una struttura sia privata, assicurarsi di dichiararla usando la parola chiave [private](../../../language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="f8576-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="f8576-110">Accesso ai valori della struttura</span><span class="sxs-lookup"><span data-stu-id="f8576-110">Access to Structure Values</span></span>

<span data-ttu-id="f8576-111">Per assegnare e recuperare valori dagli elementi di una variabile di struttura, è possibile utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8576-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="f8576-112">Si inserisce l'operatore di accesso ai membri ( `.` ) tra il nome della variabile di struttura e il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f8576-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="f8576-113">Nell'esempio seguente viene eseguito l'accesso agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo` .</span><span class="sxs-lookup"><span data-stu-id="f8576-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="f8576-114">Assegnazione di variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="f8576-114">Assigning Structure Variables</span></span>

<span data-ttu-id="f8576-115">È anche possibile assegnare una variabile a un'altra se entrambe sono dello stesso tipo di struttura.</span><span class="sxs-lookup"><span data-stu-id="f8576-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="f8576-116">In questo modo tutti gli elementi di una struttura vengono copiati negli elementi corrispondenti dell'altro.</span><span class="sxs-lookup"><span data-stu-id="f8576-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="f8576-117">Questa operazione viene illustrata nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="f8576-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="f8576-118">Se un elemento della struttura è un tipo di riferimento, ad esempio una `String` `Object` matrice, o, viene copiato il puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="f8576-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="f8576-119">Nell'esempio precedente, se `systemInfo` era inclusa una variabile oggetto, l'esempio precedente avrebbe copiato il puntatore da `mySystem` a `yourSystem` e una modifica ai dati dell'oggetto tramite una struttura verrebbe applicata quando si accede tramite l'altra struttura.</span><span class="sxs-lookup"><span data-stu-id="f8576-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8576-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8576-120">See also</span></span>

- [<span data-ttu-id="f8576-121">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="f8576-121">Data Types</span></span>](index.md)
- [<span data-ttu-id="f8576-122">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="f8576-122">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="f8576-123">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="f8576-123">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="f8576-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="f8576-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="f8576-125">Strutture</span><span class="sxs-lookup"><span data-stu-id="f8576-125">Structures</span></span>](structures.md)
- [<span data-ttu-id="f8576-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="f8576-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="f8576-127">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="f8576-127">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="f8576-128">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="f8576-128">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="f8576-129">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="f8576-129">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="f8576-130">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="f8576-130">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
