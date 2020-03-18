---
title: Analisi di stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73084308"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="baa96-102">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="baa96-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="baa96-103">Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base.</span><span class="sxs-lookup"><span data-stu-id="baa96-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="baa96-104">Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="baa96-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="baa96-105">Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`.</span><span class="sxs-lookup"><span data-stu-id="baa96-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="baa96-106">Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="baa96-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="baa96-107">Se la formattazione usa un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per stabilire come interpretare una rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="baa96-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="baa96-108">Per altre informazioni, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="baa96-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="baa96-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="baa96-109">In This Section</span></span>  
 [<span data-ttu-id="baa96-110">Analisi di stringhe numeriche</span><span class="sxs-lookup"><span data-stu-id="baa96-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="baa96-111">Descrive come eseguire la conversione di stringhe in tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="baa96-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="baa96-112">Analisi delle stringhe di data e ora</span><span class="sxs-lookup"><span data-stu-id="baa96-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="baa96-113">Descrive come eseguire la conversione di stringhe in tipi **DateTime** .NET.</span><span class="sxs-lookup"><span data-stu-id="baa96-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="baa96-114">Analisi di altre stringhe</span><span class="sxs-lookup"><span data-stu-id="baa96-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="baa96-115">Descrive come convertire le stringhe nei tipi **Char**, **Boolean** ed **Enum**.</span><span class="sxs-lookup"><span data-stu-id="baa96-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="baa96-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="baa96-116">Related Sections</span></span>  
 [<span data-ttu-id="baa96-117">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="baa96-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="baa96-118">Descrive i concetti di formattazione di base, come identificatori di formato e provider di formato.</span><span class="sxs-lookup"><span data-stu-id="baa96-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="baa96-119">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="baa96-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="baa96-120">Descrive come convertire i tipi.</span><span class="sxs-lookup"><span data-stu-id="baa96-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="baa96-121">Tipi di base</span><span class="sxs-lookup"><span data-stu-id="baa96-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="baa96-122">Descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.</span><span class="sxs-lookup"><span data-stu-id="baa96-122">Describes common operations that you can perform on .NET base types.</span></span>
