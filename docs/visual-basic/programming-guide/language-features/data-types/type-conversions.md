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
ms.openlocfilehash: 7f1a571cda4f68222c5c03c3a8fe31c29eafd8c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647213"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="15126-102">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15126-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="15126-103">Il processo di modifica di un valore da un tipo di dati a un altro tipo viene chiamato *conversione*.</span><span class="sxs-lookup"><span data-stu-id="15126-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="15126-104">Le conversioni possono essere *widening* o *restrizione*, a seconda della capacità di dati dei tipi interessati.</span><span class="sxs-lookup"><span data-stu-id="15126-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="15126-105">Sono inoltre *implicita* o *esplicita*, a seconda della sintassi nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="15126-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15126-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="15126-106">In This Section</span></span>  
 [<span data-ttu-id="15126-107">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="15126-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="15126-108">Vengono illustrate le conversioni classificate in base che il tipo di destinazione può contenere i dati.</span><span class="sxs-lookup"><span data-stu-id="15126-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="15126-109">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="15126-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="15126-110">Vengono illustrate le conversioni classificate in base al fatto che Visual Basic vengano eseguite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="15126-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="15126-111">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="15126-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="15126-112">Viene illustrata la conversione tra stringhe e numerici, `Boolean`, o i valori di data e ora.</span><span class="sxs-lookup"><span data-stu-id="15126-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="15126-113">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15126-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="15126-114">Viene illustrato come convertire un `Object` variabile a qualsiasi altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="15126-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="15126-115">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="15126-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="15126-116">I passaggi necessari per il processo di conversione tra matrici di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="15126-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15126-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="15126-117">Related Sections</span></span>  
 [<span data-ttu-id="15126-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="15126-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="15126-119">Introduce i tipi di dati Visual Basic e viene descritto come utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="15126-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="15126-120">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="15126-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="15126-121">Elenca i tipi di dati di base forniti da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15126-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="15126-122">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="15126-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="15126-123">Vengono illustrati alcuni problemi comuni che possono verificarsi quando si utilizzano tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="15126-123">Discusses some common problems that can arise when working with data types.</span></span>
