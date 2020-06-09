---
title: Aggiunta di spaziatura interna alle stringhe in .NET
description: Informazioni su come riempire le stringhe in .NET. Usare i metodi String. PadLeft e String. PadRight per aggiungere caratteri iniziali o finali per ottenere una lunghezza totale specificata.
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
ms.openlocfilehash: 5bf7023a3429e932a44ad0a0bd3409012f77cbf9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594530"
---
# <a name="padding-strings-in-net"></a>Aggiunta di spaziatura interna alle stringhe in .NET

Usare uno dei metodi <xref:System.String> riportati di seguito per creare una nuova stringa costituita da una stringa originale a cui vengono aggiunti caratteri iniziali o finali fino a una lunghezza totale specificata. Il carattere di riempimento può essere uno spazio o un carattere specificato. La stringa risultante può essere allineata a destra o a sinistra. Se la lunghezza della stringa originale è già uguale o maggiore della lunghezza totale voluta, i metodi di riempimento restituiscono la stringa originale invariata. Per altre informazioni, vedere la sezione **Returns** (Valori restituiti) dei due overload dei metodi <xref:System.String.PadLeft%2A?displayProperty=nameWithType> e <xref:System.String.PadRight%2A?displayProperty=nameWithType>.
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.|  
  
## <a name="padleft"></a>PadLeft  
 Il metodo <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata. Il metodo <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.  
  
 Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadLeft%2A> per creare una nuova stringa di venti caratteri. L'esempio visualizza "`--------Hello World!`" nella console.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 Il metodo <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento finali a una stringa originale per ottenere una lunghezza totale specificata. Il metodo <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa spazi vuoti come carattere di riempimento e il metodo <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> consente di specificare il proprio carattere di riempimento.  
  
 Nell'esempio di codice seguente viene usato il metodo <xref:System.String.PadRight%2A> per creare una nuova stringa di venti caratteri. L'esempio visualizza "`Hello World!--------`" nella console.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Operazioni di base sulle stringhe](basic-string-operations.md)
