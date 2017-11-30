---
title: Conversione dei tipi di .NET Framework in stringhe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3abe140e62f112a15a1ad1b1b2a79c14364b26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="converting-net-framework-types-to-strings"></a>Conversione dei tipi di .NET Framework in stringhe
Se si desidera convertire un tipo .NET Framework in una stringa, utilizzare il **ToString** metodo. Il **ToString** metodo restituisce una rappresentazione di stringa del tipo passato. Nella tabella seguente sono elencati i tipi .NET Framework che restituiscono una stringa in un formato corrispondente alle specifiche XML Schema (XSD).  
  
|Tipo .NET Framework|Tipo di stringa restituito|  
|-------------------------|--------------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Il formato è yyyy-MM-ddTHH:mm:sszzzzzz e i relativi subset.|  
|TimeSpan|Il formato è PnYnMnTnHnMnSad esempio, `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.|  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione di tipi di dati XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Conversione di stringhe in tipi di dati .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
