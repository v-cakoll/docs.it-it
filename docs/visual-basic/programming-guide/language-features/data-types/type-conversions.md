---
title: Conversione di tipi
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
ms.openlocfilehash: be388998da5e88f99c62128e6ad63d5a476153ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393052"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="4f0dc-102">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f0dc-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="4f0dc-103">Il processo di modifica di un valore da un tipo di dati a un altro tipo è denominato *conversione*.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="4f0dc-104">Le conversioni sono verso un tipo di dati più *ampio* o più *piccolo*, a seconda delle capacità dei dati dei tipi interessati.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="4f0dc-105">Sono anche *implicite* o *esplicite*, a seconda della sintassi nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f0dc-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4f0dc-106">In This Section</span></span>  
 [<span data-ttu-id="4f0dc-107">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="4f0dc-107">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)  
 <span data-ttu-id="4f0dc-108">Vengono illustrate le conversioni classificate in base a se il tipo di destinazione può conservare i dati.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="4f0dc-109">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="4f0dc-109">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)  
 <span data-ttu-id="4f0dc-110">Vengono illustrate le conversioni classificate in base al fatto che Visual Basic le esegua automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="4f0dc-111">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="4f0dc-111">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="4f0dc-112">Viene illustrata la conversione tra stringhe e valori numerici, `Boolean` o di data/ora.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="4f0dc-113">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f0dc-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="4f0dc-114">Viene illustrato come convertire una `Object` variabile in qualsiasi altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="4f0dc-115">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="4f0dc-115">Array Conversions</span></span>](array-conversions.md)  
 <span data-ttu-id="4f0dc-116">Illustra il processo di conversione tra matrici di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4f0dc-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4f0dc-117">Related Sections</span></span>  
 [<span data-ttu-id="4f0dc-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4f0dc-118">Data Types</span></span>](index.md)  
 <span data-ttu-id="4f0dc-119">Introduce i tipi di dati Visual Basic e ne descrive l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="4f0dc-120">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4f0dc-120">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="4f0dc-121">Elenca i tipi di dati elementari forniti da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="4f0dc-122">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4f0dc-122">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)  
 <span data-ttu-id="4f0dc-123">Vengono illustrati alcuni problemi comuni che possono verificarsi quando si utilizzano i tipi di dati di.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-123">Discusses some common problems that can arise when working with data types.</span></span>
