---
title: Matrici
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 30277507050091de6b1e9293401d61ac5e351a1f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280621"
---
# <a name="arrays"></a><span data-ttu-id="b3c15-102">Matrici</span><span class="sxs-lookup"><span data-stu-id="b3c15-102">Arrays</span></span>
<span data-ttu-id="b3c15-103">✔️ preferiscono usare le raccolte su matrici in API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="b3c15-103">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="b3c15-104">La sezione [Collections](guidelines-for-collections.md) fornisce informazioni dettagliate su come scegliere tra le raccolte e le matrici.</span><span class="sxs-lookup"><span data-stu-id="b3c15-104">The [Collections](guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="b3c15-105">❌Non usare campi di matrice di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b3c15-105">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="b3c15-106">Il campo stesso è di sola lettura e non può essere modificato, ma è possibile modificare gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="b3c15-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="b3c15-107">✔️ CONSIGLIABILE utilizzare matrici di matrici anziché matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="b3c15-107">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="b3c15-108">Una matrice irregolare è una matrice con elementi che sono anche matrici.</span><span class="sxs-lookup"><span data-stu-id="b3c15-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="b3c15-109">Le matrici che costituiscono gli elementi possono avere dimensioni diverse, causando uno spazio meno sprecato per alcuni set di dati (ad esempio, una matrice di tipo sparse) rispetto alle matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="b3c15-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="b3c15-110">Inoltre, CLR ottimizza le operazioni sugli indici su matrici di matrici, in modo che possano presentare prestazioni di runtime migliori in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="b3c15-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="b3c15-111">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b3c15-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b3c15-112">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b3c15-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b3c15-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3c15-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="b3c15-114">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b3c15-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="b3c15-115">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b3c15-115">Usage Guidelines</span></span>](usage-guidelines.md)
