---
title: Stringhe di formato di enumerazione
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
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58004fa19f2ec3b1ca7570d6ca75702510148002
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="enumeration-format-strings"></a>Stringhe di formato di enumerazione
È possibile usare il metodo <xref:System.Enum.ToString%2A?displayProperty=nameWithType> per creare un nuovo oggetto stringa che rappresenti il valore numerico, esadecimale o stringa di un membro di enumerazione. Questo metodo accetta una delle stringhe di formattazione di enumerazione per specificare il valore che si vuole venga restituito.  
  
 La tabella seguente elenca le stringhe di formattazione di enumerazione e i valori da esse restituiti. In questi identificatori di formato non viene fatta distinzione tra maiuscole e minuscole.  
  
| Stringa di formattazione | Risultato |  
| ------------- | ------ |  
| G o g | Visualizza la voce di enumerazione sotto forma di valore di stringa, se possibile; in caso contrario, visualizza il valore intero dell'istanza corrente. Se l'enumerazione viene definita con l'attributo **Flags** impostato, i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole. Se l'attributo **Flags** non è impostato, verrà visualizzato un valore non valido come voce numerica. L'esempio seguente illustra l'identificatore di formato G.<br><br>[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)] |  
| F o f | Visualizza la voce di enumerazione come valore di stringa, se possibile. Se il valore può essere visualizzato interamente come somma delle voci nell'enumerazione (anche se l'attributo **Flags** è assente), i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole. Se non è possibile determinare completamente il valore sulla base delle voci di enumerazione, il valore verrà formattato sotto forma di valore intero. L'esempio seguente illustra l'identificatore di formato F.<br><br>[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)] |  
| D o d | Visualizza la voce di enumerazione come valore intero nella rappresentazione più breve possibile. L'esempio seguente illustra l'identificatore di formato D.<br><br>[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)] |  
| X o x | Visualizza la voce di enumerazione come valore esadecimale. Il valore viene rappresentato con l'aggiunta di un numero di zeri iniziali sufficiente a raggiungere la lunghezza minima di otto cifre. L'esempio seguente illustra l'identificatore di formato X.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)] |  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un'enumerazione denominata `Colors` costituita dalle tre voci `Red`, `Blue` e `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 Dopo aver definito l'enumerazione è possibile dichiararne un'istanza nel modo seguente.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 Sarà quindi possibile usare il metodo `Color.ToString(System.String)` per visualizzare il valore di enumerazione in modi diversi, a seconda dell'identificatore di formato passato.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)
