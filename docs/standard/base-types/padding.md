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
# <a name="padding-strings-in-net"></a>Riempimento di stringhe in .NET
Utilizzare uno dei seguenti <xref:System.String> metodi per creare una nuova stringa costituita da una stringa originale è stato applicato un riempimento con caratteri di lunghezza totale specificata iniziali o finali. Il carattere di riempimento può essere costituito da spazi o da un carattere specificato e di conseguenza viene visualizzato allineato a destra o sinistra.  
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.|  
  
## <a name="padleft"></a>PadLeft  
 Il <xref:System.String.PadLeft%2A?displayProperty=nameWithType> metodo crea una nuova stringa concatenando sufficiente caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata. Il <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> metodo utilizza spazi come carattere di spaziatura interna e <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> metodo consente di specificare il propria carattere di riempimento.  
  
 Nell'esempio di codice viene illustrato come utilizzare il <xref:System.String.PadLeft%2A> metodo per creare una nuova stringa di venti caratteri. L'esempio visualizza "`--------Hello World!`" nella console.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 Il <xref:System.String.PadRight%2A?displayProperty=nameWithType> metodo crea una nuova stringa concatenando sufficiente caratteri di riempimento finali da una stringa originale per ottenere una lunghezza totale specificata. Il <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> metodo utilizza spazi come carattere di spaziatura interna e <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> metodo consente di specificare il propria carattere di riempimento.  
  
 Nell'esempio di codice viene illustrato come utilizzare il <xref:System.String.PadRight%2A> metodo per creare una nuova stringa di venti caratteri. L'esempio visualizza "`Hello World!--------`" nella console.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operazioni di base su stringhe](../../../docs/standard/base-types/basic-string-operations.md)
