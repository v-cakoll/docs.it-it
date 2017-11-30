---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="f6e05-102">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici</span><span class="sxs-lookup"><span data-stu-id="f6e05-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="f6e05-103">Esegue l'overload di <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> metodi eseguono ordinamenti predefinito utilizzando il <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f6e05-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f6e05-104">Le impostazioni cultura restituite da questi metodi possono variare dalle impostazioni cultura a causa delle differenze nell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="f6e05-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="f6e05-105">Per eliminare il comportamento delle impostazioni cultura, utilizzare uno degli overload del metodo che accetta un `comparer` parametro.</span><span class="sxs-lookup"><span data-stu-id="f6e05-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="f6e05-106">Il `comparer` parametro specifica il <xref:System.Collections.IComparer> implementazione da usare quando si confrontano gli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f6e05-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="f6e05-107">Per il parametro, specificare una classe che utilizza <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6e05-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f6e05-108">Viene fornito un esempio di una classe nell'argomento secondario di "Utilizzo della classe SortedList" il [esecuzione di operazioni di stringa indipendenti dalle impostazioni cultura nelle raccolte](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="f6e05-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="f6e05-109">**Nota** passando **CultureInfo. InvariantCulture** per un confronto metodo viene eseguito un confronto senza distinzione di impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f6e05-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="f6e05-110">Non viene tuttavia eseguito un confronto non linguistico, ad esempio per percorsi di file, chiavi del Registro di sistema e variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="f6e05-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="f6e05-111">e non sono supportate le decisioni relative alla sicurezza basate sul risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="f6e05-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="f6e05-112">Per un confronto non linguistico o il supporto per le decisioni di sicurezza basata sui risultati, l'applicazione deve utilizzare un metodo di confronto che accetta un <xref:System.StringComparison> valore.</span><span class="sxs-lookup"><span data-stu-id="f6e05-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="f6e05-113">L'applicazione deve passare quindi <xref:System.StringComparison.Ordinal>.</span><span class="sxs-lookup"><span data-stu-id="f6e05-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e05-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6e05-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="f6e05-115">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="f6e05-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
