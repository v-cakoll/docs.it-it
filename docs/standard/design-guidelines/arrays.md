---
title: Matrici
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570402"
---
# <a name="arrays"></a><span data-ttu-id="4f522-102">Matrici</span><span class="sxs-lookup"><span data-stu-id="4f522-102">Arrays</span></span>
<span data-ttu-id="4f522-103">**✓ DO** preferire l'utilizzo di raccolte sulle matrici nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="4f522-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="4f522-104">Il [raccolte](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sezione vengono fornite informazioni dettagliate su come scegliere tra le raccolte e matrici.</span><span class="sxs-lookup"><span data-stu-id="4f522-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="4f522-105">**X DO NOT** utilizzare campi di matrice di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4f522-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="4f522-106">Il campo è di sola lettura e non può essere modificato, ma gli elementi nella matrice possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="4f522-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="4f522-107">**✓ CONSIDER** utilizzando matrici di matrici anziché le matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="4f522-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="4f522-108">Una matrice di matrici è una matrice con gli elementi che sono anche le matrici.</span><span class="sxs-lookup"><span data-stu-id="4f522-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="4f522-109">Le matrici che costituiscono gli elementi possono presentare dimensioni diverse, la spazio inutilizzato sarà inferiore per alcuni set di dati (ad esempio, matrice di tipo sparse) rispetto a matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="4f522-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="4f522-110">Inoltre, CLR consente di ottimizzare operazioni sugli indici su matrici di matrici, in modo che potrebbe presentare migliori prestazioni di runtime in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="4f522-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="4f522-111">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="4f522-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4f522-112">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4f522-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f522-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f522-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="4f522-114">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="4f522-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="4f522-115">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="4f522-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
