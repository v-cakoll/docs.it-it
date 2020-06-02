---
title: Conversione dei tipi di .NET Framework in stringhe
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: d232fb0e3ea4cf3189294d6e6f43ae9270417407
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287818"
---
# <a name="converting-net-framework-types-to-strings"></a>Conversione dei tipi di .NET Framework in stringhe
Per convertire un tipo .NET Framework in una stringa, usare il metodo **ToString**, che**ToString** restituisce una rappresentazione di stringa del tipo passato. Nella tabella seguente sono elencati i tipi .NET Framework che restituiscono una stringa in un formato corrispondente alle specifiche XML Schema (XSD).  
  
|Tipo .NET Framework|Tipo di stringa restituito|  
|-------------------------|--------------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|Datetime|Il formato è yyyy-MM-ddTHH:mm:sszzzzzz e i relativi subset.|  
|TimeSpan|Il formato è PnYnMnTnHnMnSad esempio, `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.|  
  
## <a name="see-also"></a>Vedere anche

- [Conversione dei tipi di dati XML](conversion-of-xml-data-types.md)
- [Conversione delle stringhe in tipi di dati di .NET Framework](converting-strings-to-dotnet-data-types.md)
