---
title: Conversione dei tipi di .NET Framework in stringhe
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1e9b22a4bc876e9b02ec0da0439682082d2d706
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568771"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="21b69-102">Conversione dei tipi di .NET Framework in stringhe</span><span class="sxs-lookup"><span data-stu-id="21b69-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="21b69-103">Per convertire un tipo .NET Framework in una stringa, usare il metodo **ToString**,</span><span class="sxs-lookup"><span data-stu-id="21b69-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="21b69-104">che**ToString** restituisce una rappresentazione di stringa del tipo passato.</span><span class="sxs-lookup"><span data-stu-id="21b69-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="21b69-105">Nella tabella seguente sono elencati i tipi .NET Framework che restituiscono una stringa in un formato corrispondente alle specifiche XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="21b69-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="21b69-106">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21b69-106">.NET Framework type</span></span>|<span data-ttu-id="21b69-107">Tipo di stringa restituito</span><span class="sxs-lookup"><span data-stu-id="21b69-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="21b69-108">Booleano</span><span class="sxs-lookup"><span data-stu-id="21b69-108">Boolean</span></span>|<span data-ttu-id="21b69-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="21b69-109">"true", "false"</span></span>|  
|<span data-ttu-id="21b69-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="21b69-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="21b69-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="21b69-111">"INF"</span></span>|  
|<span data-ttu-id="21b69-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="21b69-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="21b69-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="21b69-113">"-INF"</span></span>|  
|<span data-ttu-id="21b69-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="21b69-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="21b69-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="21b69-115">"INF"</span></span>|  
|<span data-ttu-id="21b69-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="21b69-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="21b69-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="21b69-117">"-INF"</span></span>|  
|<span data-ttu-id="21b69-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="21b69-118">DateTime</span></span>|<span data-ttu-id="21b69-119">Il formato è yyyy-MM-ddTHH:mm:sszzzzzz e i relativi subset.</span><span class="sxs-lookup"><span data-stu-id="21b69-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="21b69-120">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="21b69-120">Timespan</span></span>|<span data-ttu-id="21b69-121">Il formato è PnYnMnTnHnMnSad esempio, `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="21b69-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21b69-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21b69-122">See Also</span></span>  
 [<span data-ttu-id="21b69-123">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="21b69-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="21b69-124">Conversione delle stringhe in tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21b69-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
