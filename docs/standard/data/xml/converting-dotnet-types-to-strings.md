---
title: Conversione dei tipi di .NET Framework in stringhe
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711077"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="f9277-102">Conversione dei tipi di .NET Framework in stringhe</span><span class="sxs-lookup"><span data-stu-id="f9277-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="f9277-103">Per convertire un tipo .NET Framework in una stringa, usare il metodo **ToString**,</span><span class="sxs-lookup"><span data-stu-id="f9277-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="f9277-104">che**ToString** restituisce una rappresentazione di stringa del tipo passato.</span><span class="sxs-lookup"><span data-stu-id="f9277-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="f9277-105">Nella tabella seguente sono elencati i tipi .NET Framework che restituiscono una stringa in un formato corrispondente alle specifiche XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="f9277-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="f9277-106">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9277-106">.NET Framework type</span></span>|<span data-ttu-id="f9277-107">Tipo di stringa restituito</span><span class="sxs-lookup"><span data-stu-id="f9277-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="f9277-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="f9277-108">Boolean</span></span>|<span data-ttu-id="f9277-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="f9277-109">"true", "false"</span></span>|  
|<span data-ttu-id="f9277-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f9277-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="f9277-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="f9277-111">"INF"</span></span>|  
|<span data-ttu-id="f9277-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f9277-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="f9277-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f9277-113">"-INF"</span></span>|  
|<span data-ttu-id="f9277-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f9277-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="f9277-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="f9277-115">"INF"</span></span>|  
|<span data-ttu-id="f9277-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f9277-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="f9277-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f9277-117">"-INF"</span></span>|  
|<span data-ttu-id="f9277-118">Datetime</span><span class="sxs-lookup"><span data-stu-id="f9277-118">DateTime</span></span>|<span data-ttu-id="f9277-119">Il formato è yyyy-MM-ddTHH:mm:sszzzzzz e i relativi subset.</span><span class="sxs-lookup"><span data-stu-id="f9277-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="f9277-120">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="f9277-120">Timespan</span></span>|<span data-ttu-id="f9277-121">Il formato è PnYnMnTnHnMnSad esempio, `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="f9277-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9277-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f9277-122">See also</span></span>

- [<span data-ttu-id="f9277-123">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="f9277-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [<span data-ttu-id="f9277-124">Conversione delle stringhe in tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9277-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
