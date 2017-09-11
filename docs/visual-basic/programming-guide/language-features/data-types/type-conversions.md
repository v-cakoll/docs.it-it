---
title: Conversioni di tipi in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion
- conversions, data type
- changing data types
- data type conversion
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 61606572dd1f10dc5df4ed4baec02f230a23c8d6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="eeb25-102">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eeb25-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="eeb25-103">Il processo di modifica di un valore da un tipo di dati a un altro tipo è denominato *conversione*.</span><span class="sxs-lookup"><span data-stu-id="eeb25-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="eeb25-104">Le conversioni sono *ampliamento* o *narrowing*, a seconda della capacità di dati dei tipi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="eeb25-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="eeb25-105">Sono inoltre *implicita* o *esplicita*, a seconda della sintassi nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eeb25-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eeb25-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="eeb25-106">In This Section</span></span>  
 [<span data-ttu-id="eeb25-107">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="eeb25-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="eeb25-108">Vengono illustrate le conversioni classificate in base a se il tipo di destinazione può contenere i dati.</span><span class="sxs-lookup"><span data-stu-id="eeb25-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="eeb25-109">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="eeb25-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="eeb25-110">Vengono illustrate le conversioni classificate in base al fatto [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] vengano eseguite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eeb25-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="eeb25-111">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="eeb25-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="eeb25-112">Viene illustrata la conversione tra stringhe e numerico, `Boolean`, o valori data/ora.</span><span class="sxs-lookup"><span data-stu-id="eeb25-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="eeb25-113">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eeb25-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="eeb25-114">Viene illustrato come convertire un `Object` variabile in qualsiasi altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="eeb25-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="eeb25-115">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="eeb25-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="eeb25-116">Viene illustrato il processo di conversione tra le matrici di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="eeb25-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eeb25-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="eeb25-117">Related Sections</span></span>  
 [<span data-ttu-id="eeb25-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="eeb25-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="eeb25-119">Introduce il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati e viene descritto come utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="eeb25-119">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="eeb25-120">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="eeb25-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="eeb25-121">Vengono elencati i tipi di dati di base forniti da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="eeb25-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="eeb25-122">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="eeb25-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="eeb25-123">Vengono illustrati alcuni problemi comuni che possono verificarsi quando si lavora con tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="eeb25-123">Discusses some common problems that can arise when working with data types.</span></span>
