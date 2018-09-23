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
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46705786"
---
# <a name="arrays"></a><span data-ttu-id="eca10-102">Matrici</span><span class="sxs-lookup"><span data-stu-id="eca10-102">Arrays</span></span>
<span data-ttu-id="eca10-103">**✓ DO** preferire l'utilizzo di raccolte sulle matrici nelle API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="eca10-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="eca10-104">Il [raccolte](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sezione vengono fornite informazioni dettagliate su come scegliere tra le raccolte e matrici.</span><span class="sxs-lookup"><span data-stu-id="eca10-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="eca10-105">**X DO NOT** utilizzare campi di matrice di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="eca10-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="eca10-106">Il campo stesso è di sola lettura e non può essere modificato, ma gli elementi della matrice possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="eca10-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="eca10-107">**✓ CONSIDER** utilizzando matrici di matrici anziché le matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="eca10-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="eca10-108">Una matrice di matrici è una matrice con elementi che sono anche le matrici.</span><span class="sxs-lookup"><span data-stu-id="eca10-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="eca10-109">Le matrici che costituiscono gli elementi possono essere di dimensioni diverse, spazio inutilizzato sarà inferiore per alcuni set di dati (ad esempio, matrice di tipo sparse) rispetto a matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="eca10-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="eca10-110">Inoltre, CLR ottimizza le operazioni di indice in matrici di matrici, in modo che potrebbe presentare prestazioni di runtime migliori in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="eca10-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="eca10-111">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="eca10-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="eca10-112">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="eca10-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca10-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca10-113">See also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="eca10-114">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="eca10-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="eca10-115">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="eca10-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
