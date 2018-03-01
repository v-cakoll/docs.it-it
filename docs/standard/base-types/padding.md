---
title: Aggiunta di spaziatura interna alle stringhe in .NET
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea903c1f950e7c226e043c1fa7276a66126b2512
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="b1f8a-102">Aggiunta di spaziatura interna alle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="b1f8a-102">Padding Strings in .NET</span></span>
<span data-ttu-id="b1f8a-103">Usare uno dei metodi <xref:System.String> riportati di seguito per creare una nuova stringa costituita da una stringa originale a cui vengono aggiunti caratteri iniziali o finali fino a una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="b1f8a-104">Il carattere di riempimento può essere costituito da spazi o da un carattere specificato e di conseguenza viene visualizzato allineato a destra o sinistra.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="b1f8a-105">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="b1f8a-105">Method name</span></span>|<span data-ttu-id="b1f8a-106">Usa</span><span class="sxs-lookup"><span data-stu-id="b1f8a-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="b1f8a-107">Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="b1f8a-108">Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="b1f8a-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="b1f8a-109">PadLeft</span></span>  
 <span data-ttu-id="b1f8a-110">Il metodo <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b1f8a-111">Il metodo <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="b1f8a-112">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadLeft%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b1f8a-113">L'esempio visualizza "`--------Hello World!`" nella console.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="b1f8a-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="b1f8a-114">PadRight</span></span>  
 <span data-ttu-id="b1f8a-115">Il metodo <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento finali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b1f8a-116">Il metodo <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="b1f8a-117">Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadRight%2A> per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b1f8a-118">L'esempio visualizza "`Hello World!--------`" nella console.</span><span class="sxs-lookup"><span data-stu-id="b1f8a-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b1f8a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1f8a-119">See Also</span></span>  
 [<span data-ttu-id="b1f8a-120">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="b1f8a-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
