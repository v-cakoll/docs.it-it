---
title: Analisi di stringhe in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a>Analisi di stringhe in .NET
Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base. Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora. Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`. Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni. Se la formattazione usa un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per stabilire come interpretare una rappresentazione di stringa. Per altre informazioni, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Analisi di stringhe numeriche](../../../docs/standard/base-types/parsing-numeric.md)  
 Descrive come eseguire la conversione di stringhe in tipi numerici .NET.  
  
 [Analisi di stringhe di data e ora](../../../docs/standard/base-types/parsing-datetime.md)  
 Descrive come eseguire la conversione di stringhe in tipi **DateTime** .NET.  
  
 [Analisi di altre stringhe](../../../docs/standard/base-types/parsing-other.md)  
 Descrive come convertire le stringhe nei tipi **Char**, **Boolean** ed **Enum**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)  
 Descrive i concetti di formattazione di base, come identificatori di formato e provider di formato.  
  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)  
 Descrive come convertire i tipi.  
  
 [Tipi di base](../../../docs/standard/base-types/index.md)  
 Descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.
