---
title: Interfacce di hosting
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: d1668f52ff305ec36fb520c7828c822537da0d02
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616099"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="8d392-102">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8d392-102">Hosting Interfaces</span></span>
<span data-ttu-id="8d392-103">In questa sezione vengono descritte le interfacce che gli host non gestiti possono utilizzare per integrare il Common Language Runtime (CLR) nelle relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d392-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="8d392-104">Le interfacce di hosting .NET Framework versione 2,0 sostituiscono le interfacce .NET Framework versione 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="8d392-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="8d392-105">Esistono differenze significative tra i due set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="8d392-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="8d392-106">La combinazione di questi elementi può causare un comportamento imprevisto e non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="8d392-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="8d392-107">Le .NET Framework versioni 3,0 e 3,5 utilizzano le interfacce di hosting della versione 2,0 di .NET Framework e non introducono alcuna funzionalità di hosting.</span><span class="sxs-lookup"><span data-stu-id="8d392-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="8d392-108">Le interfacce di hosting .NET Framework 4 sostituiscono le interfacce .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8d392-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8d392-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8d392-109">In This Section</span></span>  
 [<span data-ttu-id="8d392-110">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="8d392-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="8d392-111">Descrive le interfacce di hosting introdotte nelle .NET Framework versioni 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="8d392-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="8d392-112">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="8d392-112">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="8d392-113">Descrive le interfacce di hosting introdotte nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8d392-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="8d392-114">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="8d392-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="8d392-115">Descrive le interfacce di hosting introdotte nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8d392-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8d392-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8d392-116">Related Sections</span></span>  
 [<span data-ttu-id="8d392-117">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="8d392-117">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="8d392-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="8d392-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="8d392-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="8d392-119">Hosting Enumerations</span></span>](hosting-enumerations.md)  
  
 [<span data-ttu-id="8d392-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="8d392-120">Hosting Structures</span></span>](hosting-structures.md)  
  
 [<span data-ttu-id="8d392-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="8d392-121">Hosting</span></span>](index.md)  
  
 <span data-ttu-id="8d392-122">[Host di runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8d392-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
