---
title: Analisi di stringhe in .NET
description: Analisi di stringhe in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.contentlocale: it-it
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a><span data-ttu-id="e79ea-104">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e79ea-104">Parsing strings in .NET</span></span>

<span data-ttu-id="e79ea-105">Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base.</span><span class="sxs-lookup"><span data-stu-id="e79ea-105">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="e79ea-106">Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="e79ea-106">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="e79ea-107">Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`.</span><span class="sxs-lookup"><span data-stu-id="e79ea-107">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="e79ea-108">Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="e79ea-108">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="e79ea-109">Se la formattazione usa un oggetto che implementa l'interfaccia [IFormatProvider](xref:System.IFormatProvider) per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia [IFormatProvider](xref:System.IFormatProvider) per stabilire come interpretare una rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="e79ea-109">Just as formatting uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to provide culture-sensitive formatting information, parsing also uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="e79ea-110">Per altre informazioni, vedere [Formattazione di tipi in .NET](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="e79ea-110">For more information, see [Formatting Types in .NET](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e79ea-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e79ea-111">In This Section</span></span>

<span data-ttu-id="e79ea-112">[Analisi di stringhe numeriche in .NET](parsing-numeric.md): viene descritto come convertire le stringhe in tipi numerici di .NET.</span><span class="sxs-lookup"><span data-stu-id="e79ea-112">[Parsing Numeric Strings in .NET](parsing-numeric.md) - Describes how to convert strings into .NET numeric types.</span></span>

<span data-ttu-id="e79ea-113">[Analisi di stringhe di data e ora in .NET](parsing-datetime.md): viene descritto come convertire le stringhe in tipi `DateTime` di .NET.</span><span class="sxs-lookup"><span data-stu-id="e79ea-113">[Parsing Date and Time Strings in .NET](parsing-datetime.md) - Describes how to convert strings into .NET `DateTime` types.</span></span>

<span data-ttu-id="e79ea-114">[Analisi di altre stringhe in .NET](parsing-other.md): viene descritto come convertire le stringhe nei tipi [Char](xref:System.Char), [Boolean](xref:System.Boolean) ed [Enum](xref:System.Enum).</span><span class="sxs-lookup"><span data-stu-id="e79ea-114">[Parsing Other Strings in .NET](parsing-other.md) - Describes how to convert strings into [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) types.</span></span>

<span data-ttu-id="e79ea-115">[Formattazione di tipi in .NET](formatting-types.md): descrive i concetti di formattazione di base, come identificatori di formato e provider di formato.</span><span class="sxs-lookup"><span data-stu-id="e79ea-115">[Formatting Types in .NET](formatting-types.md) - Describes basic formatting concepts like format specifiers and format providers.</span></span>

<span data-ttu-id="e79ea-116">[Conversione di tipi in .NET](type-conversion.md): viene descritta la procedura di conversione dei tipi.</span><span class="sxs-lookup"><span data-stu-id="e79ea-116">[Type Conversion in .NET](type-conversion.md) - Describes how to convert types.</span></span>

<span data-ttu-id="e79ea-117">[Uso dei tipi di base in .NET](index.md): descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.</span><span class="sxs-lookup"><span data-stu-id="e79ea-117">[Working with Base Types in .NET](index.md) - Describes common operations that you can perform on .NET base types.</span></span>


