---
title: Analisi di stringhe in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="e8633-102">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e8633-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="e8633-103">Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base.</span><span class="sxs-lookup"><span data-stu-id="e8633-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="e8633-104">Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="e8633-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="e8633-105">Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`.</span><span class="sxs-lookup"><span data-stu-id="e8633-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="e8633-106">Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="e8633-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="e8633-107">Come nella formattazione viene utilizzato un oggetto che implementa il <xref:System.IFormatProvider> interfaccia per fornire informazioni di formattazione delle impostazioni cultura, utilizza anche nell'analisi di un oggetto che implementa il <xref:System.IFormatProvider> interfaccia per determinare come interpretare una rappresentazione di stringa .</span><span class="sxs-lookup"><span data-stu-id="e8633-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="e8633-108">Per ulteriori informazioni, vedere [formattazione dei tipi di](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="e8633-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8633-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e8633-109">In This Section</span></span>  
 [<span data-ttu-id="e8633-110">Analisi di stringhe numeriche</span><span class="sxs-lookup"><span data-stu-id="e8633-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="e8633-111">Viene descritto come convertire le stringhe in tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="e8633-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="e8633-112">Analisi di stringhe di data e ora</span><span class="sxs-lookup"><span data-stu-id="e8633-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="e8633-113">Viene descritto come convertire le stringhe in .NET **DateTime** tipi.</span><span class="sxs-lookup"><span data-stu-id="e8633-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="e8633-114">Analisi di altre stringhe</span><span class="sxs-lookup"><span data-stu-id="e8633-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="e8633-115">Viene descritto come convertire le stringhe in **Char**, **booleano**, e **Enum** tipi.</span><span class="sxs-lookup"><span data-stu-id="e8633-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e8633-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e8633-116">Related Sections</span></span>  
 [<span data-ttu-id="e8633-117">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="e8633-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="e8633-118">Descrive i concetti di formattazione di base come identificatori di formato e provider di formato.</span><span class="sxs-lookup"><span data-stu-id="e8633-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="e8633-119">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="e8633-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="e8633-120">Viene descritto come convertire i tipi.</span><span class="sxs-lookup"><span data-stu-id="e8633-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="e8633-121">Tipi di base</span><span class="sxs-lookup"><span data-stu-id="e8633-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="e8633-122">Descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.</span><span class="sxs-lookup"><span data-stu-id="e8633-122">Describes common operations that you can perform on .NET base types.</span></span>
