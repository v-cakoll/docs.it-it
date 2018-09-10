---
title: Aggiunta di spaziatura interna alle stringhe in .NET
ms.date: 03/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f58e1c3a9e42f48ecc219a2db1649051f9ca20b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890727"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="a9d8a-102">Aggiunta di spaziatura interna alle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="a9d8a-102">Padding Strings in .NET</span></span>

<span data-ttu-id="a9d8a-103">Usare uno dei metodi <xref:System.String> riportati di seguito per creare una nuova stringa costituita da una stringa originale a cui vengono aggiunti caratteri iniziali o finali fino a una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="a9d8a-104">Il carattere di riempimento può essere uno spazio o un carattere specificato.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-104">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="a9d8a-105">La stringa risultante può essere allineata a destra o a sinistra.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-105">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="a9d8a-106">Se la lunghezza della stringa originale è già uguale o maggiore della lunghezza totale voluta, i metodi di riempimento restituiscono la stringa originale invariata. Per altre informazioni, vedere la sezione **Returns** (Valori restituiti) dei due overload dei metodi <xref:System.String.PadLeft%2A?displayProperty=nameWithType> e <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-106">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="a9d8a-107">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="a9d8a-107">Method name</span></span>|<span data-ttu-id="a9d8a-108">Usa</span><span class="sxs-lookup"><span data-stu-id="a9d8a-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="a9d8a-109">Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-109">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="a9d8a-110">Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-110">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="a9d8a-111">PadLeft</span><span class="sxs-lookup"><span data-stu-id="a9d8a-111">PadLeft</span></span>  
 <span data-ttu-id="a9d8a-112">Il metodo <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-112">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="a9d8a-113">Il metodo <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-113">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="a9d8a-114">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadLeft%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-114">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="a9d8a-115">L'esempio visualizza "`--------Hello World!`" nella console.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-115">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="a9d8a-116">PadRight</span><span class="sxs-lookup"><span data-stu-id="a9d8a-116">PadRight</span></span>  
 <span data-ttu-id="a9d8a-117">Il metodo <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento finali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-117">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="a9d8a-118">Il metodo <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-118">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="a9d8a-119">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadRight%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-119">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="a9d8a-120">L'esempio visualizza "`Hello World!--------`" nella console.</span><span class="sxs-lookup"><span data-stu-id="a9d8a-120">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a9d8a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9d8a-121">See also</span></span>

- [<span data-ttu-id="a9d8a-122">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="a9d8a-122">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
