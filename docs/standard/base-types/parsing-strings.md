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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a>Analisi di stringhe in .NET
Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base. Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora. Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`. Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni. Come nella formattazione viene utilizzato un oggetto che implementa il <xref:System.IFormatProvider> interfaccia per fornire informazioni di formattazione delle impostazioni cultura, utilizza anche nell'analisi di un oggetto che implementa il <xref:System.IFormatProvider> interfaccia per determinare come interpretare una rappresentazione di stringa . Per ulteriori informazioni, vedere [formattazione dei tipi di](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Analisi di stringhe numeriche](../../../docs/standard/base-types/parsing-numeric.md)  
 Viene descritto come convertire le stringhe in tipi numerici .NET.  
  
 [Analisi di stringhe di data e ora](../../../docs/standard/base-types/parsing-datetime.md)  
 Viene descritto come convertire le stringhe in .NET **DateTime** tipi.  
  
 [Analisi di altre stringhe](../../../docs/standard/base-types/parsing-other.md)  
 Viene descritto come convertire le stringhe in **Char**, **booleano**, e **Enum** tipi.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)  
 Descrive i concetti di formattazione di base come identificatori di formato e provider di formato.  
  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)  
 Viene descritto come convertire i tipi.  
  
 [Tipi di base](../../../docs/standard/base-types/index.md)  
 Descrive le operazioni comuni che è possibile eseguire sui tipi di base di .NET.
