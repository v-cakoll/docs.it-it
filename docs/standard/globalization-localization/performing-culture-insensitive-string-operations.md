---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 79ff899e2964ae2c1e90b7178616c612dddf6d86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287506"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="7391c-102">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="7391c-102">Performing culture-insensitive string operations</span></span>
<span data-ttu-id="7391c-103">Per la maggior parte, i metodi di .NET Framework che eseguono operazioni sulle stringhe dipendenti dalle impostazioni cultura forniscono, per impostazione predefinita, overload dei metodi che consentono di specificare in modo esplicito le impostazioni cultura da usare mediante il passaggio di un parametro <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="7391c-103">Most .NET Framework methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="7391c-104">Questi overload consentono di eliminare le variazioni legate alle impostazioni cultura in mapping tra maiuscole e minuscole e regole di ordinamento e garantiscono risultati indipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7391c-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="7391c-105">In questa sezione vengono forniti gli argomenti elencati di seguito, in cui viene illustrato come eseguire operazioni sulle stringhe indipendenti dalle impostazioni cultura usando metodi .NET Framework che per impostazione predefinita sono dipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7391c-105">This section provides the following topics to demonstrate how to perform culture-insensitive string operations using .NET Framework methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7391c-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7391c-106">In this section</span></span>  
 [<span data-ttu-id="7391c-107">Esecuzione di confronti di stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="7391c-107">Performing Culture-Insensitive String Comparisons</span></span>](performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="7391c-108">Descrive come usare i metodi <xref:System.String.Compare%2A?displayProperty=nameWithType> e <xref:System.String.CompareTo%2A?displayProperty=nameWithType> per eseguire confronti tra stringhe indipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7391c-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="7391c-109">Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="7391c-109">Performing Culture-Insensitive Case Changes</span></span>](performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="7391c-110">Descrive come usare i metodi <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> per eseguire modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7391c-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="7391c-111">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte</span><span class="sxs-lookup"><span data-stu-id="7391c-111">Performing Culture-Insensitive String Operations in Collections</span></span>](performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="7391c-112">Descrive come usare <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> (classe), <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> e <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="7391c-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="7391c-113">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici</span><span class="sxs-lookup"><span data-stu-id="7391c-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="7391c-114">Descrive come usare i metodi <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle matrici.</span><span class="sxs-lookup"><span data-stu-id="7391c-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7391c-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7391c-115">Related sections</span></span>  
 [<span data-ttu-id="7391c-116">Operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="7391c-116">Culture-Insensitive String Operations</span></span>](culture-insensitive-string-operations.md)  
 <span data-ttu-id="7391c-117">Vengono descritti i motivi per cui è opportuno tenere in considerazione le impostazioni cultura in occasione dell'esecuzione di operazioni sulle stringhe e vengono fornite indicazioni sui casi in cui devono essere eseguite operazioni dipendenti dalle impostazioni cultura o operazioni indipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7391c-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="7391c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7391c-118">See also</span></span>

- <span data-ttu-id="7391c-119">[Sorting Weight Tables (for .NET on Windows systems)](https://www.microsoft.com/download/details.aspx?id=10921) (Tabelle di ordinamento spessore - Per .NET in sistemi Windows)</span><span class="sxs-lookup"><span data-stu-id="7391c-119">[Sorting Weight Tables (for .NET on Windows systems)](https://www.microsoft.com/download/details.aspx?id=10921)</span></span>
- <span data-ttu-id="7391c-120">[Default Unicode Collation Element Table (for .NET Core on Linux and macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt) (Tabella degli elementi delle regole di confronto Unicode predefinite - Per .NET Core in Linux e MacOS)</span><span class="sxs-lookup"><span data-stu-id="7391c-120">[Default Unicode Collation Element Table (for .NET Core on Linux and macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)</span></span>
