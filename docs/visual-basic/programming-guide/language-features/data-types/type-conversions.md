---
title: Conversioni di tipi in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 026b2a250abfac0782feb0946bc50a94f504f7ed
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800664"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="19004-102">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19004-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="19004-103">Il processo di modifica di un valore da un tipo di dati in un altro tipo viene definito *conversione*.</span><span class="sxs-lookup"><span data-stu-id="19004-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="19004-104">Sono conversioni *widening* oppure *narrowing*, in base a capacità di dati dei tipi interessati.</span><span class="sxs-lookup"><span data-stu-id="19004-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="19004-105">Sono inoltre *implicita* oppure *esplicite*, a seconda di sintassi nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="19004-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19004-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="19004-106">In This Section</span></span>  
 [<span data-ttu-id="19004-107">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="19004-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="19004-108">Vengono illustrate le conversioni classificate in base al fatto che il tipo di destinazione può contenere i dati.</span><span class="sxs-lookup"><span data-stu-id="19004-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="19004-109">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="19004-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="19004-110">Vengono illustrate le conversioni classificate in base al fatto che Visual Basic vengano eseguite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="19004-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="19004-111">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="19004-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="19004-112">Viene illustrata la conversione tra stringhe e numerici, `Boolean`, o i valori di data/ora.</span><span class="sxs-lookup"><span data-stu-id="19004-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="19004-113">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19004-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="19004-114">Viene illustrato come convertire un `Object` variabile con un altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="19004-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="19004-115">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="19004-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="19004-116">Viene illustrato il processo di conversione tra matrici di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="19004-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="19004-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="19004-117">Related Sections</span></span>  
 [<span data-ttu-id="19004-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="19004-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="19004-119">Introduce i tipi di dati di Visual Basic e viene descritto come utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="19004-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="19004-120">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="19004-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="19004-121">Elenca i tipi di dati elementare forniti da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="19004-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="19004-122">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="19004-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="19004-123">Vengono illustrati alcuni problemi comuni che possono verificarsi quando si lavora con tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="19004-123">Discusses some common problems that can arise when working with data types.</span></span>
