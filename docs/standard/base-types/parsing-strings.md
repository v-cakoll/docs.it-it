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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="361a2-102">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="361a2-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="361a2-103">Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base.</span><span class="sxs-lookup"><span data-stu-id="361a2-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="361a2-104">Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="361a2-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="361a2-105">Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`.</span><span class="sxs-lookup"><span data-stu-id="361a2-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="361a2-106">Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="361a2-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="361a2-107">Se la formattazione usa un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per stabilire come interpretare una rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="361a2-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="361a2-108">Per altre informazioni, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="361a2-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="361a2-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="361a2-109">In This Section</span></span>  
 [<span data-ttu-id="361a2-110">Analisi di stringhe numeriche</span><span class="sxs-lookup"><span data-stu-id="361a2-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="361a2-111">Descrive come eseguire la conversione di stringhe in tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="361a2-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="361a2-112">Analisi di stringhe di data e ora</span><span class="sxs-lookup"><span data-stu-id="361a2-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="361a2-113">Descrive come eseguire la conversione di stringhe in tipi **DateTime** .NET.</span><span class="sxs-lookup"><span data-stu-id="361a2-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="361a2-114">Analisi di altre stringhe</span><span class="sxs-lookup"><span data-stu-id="361a2-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="361a2-115">Descrive come convertire le stringhe nei tipi **Char**, **Boolean** ed **Enum**.</span><span class="sxs-lookup"><span data-stu-id="361a2-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="361a2-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="361a2-116">Related Sections</span></span>  
 [<span data-ttu-id="361a2-117">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="361a2-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="361a2-118">Descrive i concetti di formattazione di base, come identificatori di formato e provider di formato.</span><span class="sxs-lookup"><span data-stu-id="361a2-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="361a2-119">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="361a2-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="361a2-120">Descrive come convertire i tipi.</span><span class="sxs-lookup"><span data-stu-id="361a2-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="361a2-121">Tipi di base</span><span class="sxs-lookup"><span data-stu-id="361a2-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="361a2-122">Descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.</span><span class="sxs-lookup"><span data-stu-id="361a2-122">Describes common operations that you can perform on .NET base types.</span></span>
