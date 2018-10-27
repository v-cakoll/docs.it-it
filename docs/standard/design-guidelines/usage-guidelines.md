---
title: Linee guida sull'utilizzo
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e583bf7768c60477effb6c1cf9b838ae4c8c182
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50042532"
---
# <a name="usage-guidelines"></a>Linee guida sull'utilizzo

In questa sezione contiene le linee guida per l'utilizzo di tipi comuni per le API accessibili pubblicamente. Deve gestire con utilizzo diretto di tipi di Framework (ad esempio, gli attributi di serializzazione) e l'overload degli operatori comuni integrati.
  
Il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia non è coperto in questa sezione, ma verrà discusso il [modello Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sezione.

> [!NOTE]
> Per linee guida e informazioni aggiuntive sulle altre comuni, tipi di .NET Framework incorporati, vedere gli argomenti di riferimento per gli elementi seguenti: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>Contenuto della sezione

[Matrici](arrays.md)  
[Attributi](attributes.md)  
[Raccolte](guidelines-for-collections.md)  
[Serializzazione](serialization.md)  
[Uso di System.Xml](system-xml-usage.md)  
[Operatori di uguaglianza](equality-operators.md)  

*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
