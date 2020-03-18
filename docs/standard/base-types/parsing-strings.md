---
title: Analisi di stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73084308"
---
# <a name="parsing-strings-in-net"></a>Analisi di stringhe in .NET
Un'operazione di analisi converte una stringa che rappresenta un tipo di base .NET in quel tipo di base. Ad esempio, un'operazione di analisi viene usata per convertire una stringa in un numero a virgola mobile o in un valore di data e ora. Il metodo più comunemente usato per eseguire un'operazione di analisi è il metodo `Parse`. Poiché l'analisi è l'operazione inversa della formattazione (che comporta la conversione di un tipo di base nella relativa rappresentazione di stringa), vengono applicate molte delle stesse regole e convenzioni. Se la formattazione usa un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per visualizzare informazioni di formattazione dipendenti dalle impostazioni cultura, l'analisi usa anche un oggetto che implementa l'interfaccia <xref:System.IFormatProvider> per stabilire come interpretare una rappresentazione di stringa. Per altre informazioni, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Analisi di stringhe numeriche](../../../docs/standard/base-types/parsing-numeric.md)  
 Descrive come eseguire la conversione di stringhe in tipi numerici .NET.  
  
 [Analisi delle stringhe di data e ora](../../../docs/standard/base-types/parsing-datetime.md)  
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
