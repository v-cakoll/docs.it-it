---
title: Riempimento di stringhe in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="410f0-102">Riempimento di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="410f0-102">Padding Strings in .NET</span></span>
<span data-ttu-id="410f0-103">Utilizzare uno dei seguenti <xref:System.String> metodi per creare una nuova stringa costituita da una stringa originale è stato applicato un riempimento con caratteri di lunghezza totale specificata iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="410f0-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="410f0-104">Il carattere di riempimento può essere costituito da spazi o da un carattere specificato e di conseguenza viene visualizzato allineato a destra o sinistra.</span><span class="sxs-lookup"><span data-stu-id="410f0-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="410f0-105">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="410f0-105">Method name</span></span>|<span data-ttu-id="410f0-106">Uso</span><span class="sxs-lookup"><span data-stu-id="410f0-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="410f0-107">Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="410f0-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="410f0-108">Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="410f0-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="410f0-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="410f0-109">PadLeft</span></span>  
 <span data-ttu-id="410f0-110">Il <xref:System.String.PadLeft%2A?displayProperty=nameWithType> metodo crea una nuova stringa concatenando sufficiente caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="410f0-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="410f0-111">Il <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> metodo utilizza spazi come carattere di spaziatura interna e <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> metodo consente di specificare il propria carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="410f0-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="410f0-112">Nell'esempio di codice viene illustrato come utilizzare il <xref:System.String.PadLeft%2A> metodo per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="410f0-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="410f0-113">L'esempio visualizza "`--------Hello World!`" nella console.</span><span class="sxs-lookup"><span data-stu-id="410f0-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="410f0-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="410f0-114">PadRight</span></span>  
 <span data-ttu-id="410f0-115">Il <xref:System.String.PadRight%2A?displayProperty=nameWithType> metodo crea una nuova stringa concatenando sufficiente caratteri di riempimento finali da una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="410f0-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="410f0-116">Il <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> metodo utilizza spazi come carattere di spaziatura interna e <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> metodo consente di specificare il propria carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="410f0-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="410f0-117">Nell'esempio di codice viene illustrato come utilizzare il <xref:System.String.PadRight%2A> metodo per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="410f0-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="410f0-118">L'esempio visualizza "`Hello World!--------`" nella console.</span><span class="sxs-lookup"><span data-stu-id="410f0-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="410f0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="410f0-119">See Also</span></span>  
 [<span data-ttu-id="410f0-120">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="410f0-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
