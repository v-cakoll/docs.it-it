---
title: Analisi di stringhe in .NET
description: Informazioni sull'analisi delle stringhe in .NET. L'analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base. L'analisi è l'operazione inversa per la formattazione.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 5e297c8f689fdabc268ee6e269a7969155befe7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769288"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="77e03-105">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="77e03-105">Parsing Strings in .NET</span></span>
<span data-ttu-id="77e03-106">Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base.</span><span class="sxs-lookup"><span data-stu-id="77e03-106">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="77e03-107">Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="77e03-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="77e03-108">Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`.</span><span class="sxs-lookup"><span data-stu-id="77e03-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="77e03-109">Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="77e03-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="77e03-110">Se la formattazione usa un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per stabilire come interpretare una rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="77e03-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="77e03-111">Per altre informazioni, vedere [Formattazione di tipi](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="77e03-111">For more information, see [Formatting Types](formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77e03-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="77e03-112">In This Section</span></span>  
 [<span data-ttu-id="77e03-113">Analisi di stringhe numeriche</span><span class="sxs-lookup"><span data-stu-id="77e03-113">Parsing Numeric Strings</span></span>](parsing-numeric.md)  
 <span data-ttu-id="77e03-114">Descrive come eseguire la conversione di stringhe in tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="77e03-114">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="77e03-115">Analisi di stringhe di data e ora</span><span class="sxs-lookup"><span data-stu-id="77e03-115">Parsing Date and Time Strings</span></span>](parsing-datetime.md)  
 <span data-ttu-id="77e03-116">Descrive come eseguire la conversione di stringhe in tipi **DateTime** .NET.</span><span class="sxs-lookup"><span data-stu-id="77e03-116">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="77e03-117">Analisi di altre stringhe</span><span class="sxs-lookup"><span data-stu-id="77e03-117">Parsing Other Strings</span></span>](parsing-other.md)  
 <span data-ttu-id="77e03-118">Descrive come convertire le stringhe nei tipi **Char**, **Boolean** ed **Enum**.</span><span class="sxs-lookup"><span data-stu-id="77e03-118">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77e03-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="77e03-119">Related Sections</span></span>  
 [<span data-ttu-id="77e03-120">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="77e03-120">Formatting Types</span></span>](formatting-types.md)  
 <span data-ttu-id="77e03-121">Descrive i concetti di formattazione di base, come identificatori di formato e provider di formato.</span><span class="sxs-lookup"><span data-stu-id="77e03-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="77e03-122">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="77e03-122">Type Conversion in .NET</span></span>](type-conversion.md)  
 <span data-ttu-id="77e03-123">Descrive come convertire i tipi.</span><span class="sxs-lookup"><span data-stu-id="77e03-123">Describes how to convert types.</span></span>
