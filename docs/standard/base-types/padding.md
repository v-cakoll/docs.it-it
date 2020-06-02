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
ms.openlocfilehash: 83d4b348c4de537d9a71363d34898a50a6a74cb3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290396"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="1e974-102">Aggiunta di spaziatura interna alle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="1e974-102">Padding Strings in .NET</span></span>

<span data-ttu-id="1e974-103">Usare uno dei metodi <xref:System.String> riportati di seguito per creare una nuova stringa costituita da una stringa originale a cui vengono aggiunti caratteri iniziali o finali fino a una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="1e974-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="1e974-104">Il carattere di riempimento può essere uno spazio o un carattere specificato.</span><span class="sxs-lookup"><span data-stu-id="1e974-104">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="1e974-105">La stringa risultante può essere allineata a destra o a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1e974-105">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="1e974-106">Se la lunghezza della stringa originale è già uguale o maggiore della lunghezza totale voluta, i metodi di riempimento restituiscono la stringa originale invariata. Per altre informazioni, vedere la sezione **Returns** (Valori restituiti) dei due overload dei metodi <xref:System.String.PadLeft%2A?displayProperty=nameWithType> e <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e974-106">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="1e974-107">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="1e974-107">Method name</span></span>|<span data-ttu-id="1e974-108">Uso</span><span class="sxs-lookup"><span data-stu-id="1e974-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="1e974-109">Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="1e974-109">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="1e974-110">Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="1e974-110">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="1e974-111">PadLeft</span><span class="sxs-lookup"><span data-stu-id="1e974-111">PadLeft</span></span>  
 <span data-ttu-id="1e974-112">Il metodo <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="1e974-112">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="1e974-113">Il metodo <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="1e974-113">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="1e974-114">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadLeft%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="1e974-114">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="1e974-115">L'esempio visualizza "`--------Hello World!`" nella console.</span><span class="sxs-lookup"><span data-stu-id="1e974-115">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="1e974-116">PadRight</span><span class="sxs-lookup"><span data-stu-id="1e974-116">PadRight</span></span>  
 <span data-ttu-id="1e974-117">Il metodo <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento finali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="1e974-117">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="1e974-118">Il metodo <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="1e974-118">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="1e974-119">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadRight%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="1e974-119">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="1e974-120">L'esempio visualizza "`Hello World!--------`" nella console.</span><span class="sxs-lookup"><span data-stu-id="1e974-120">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1e974-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e974-121">See also</span></span>

- [<span data-ttu-id="1e974-122">Operazioni di base sulle stringhe</span><span class="sxs-lookup"><span data-stu-id="1e974-122">Basic String Operations</span></span>](basic-string-operations.md)
