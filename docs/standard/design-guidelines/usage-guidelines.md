---
title: Linee guida per l'utilizzo
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 761570b899a2a36391eb81dc7f42e13fff1f14ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778807"
---
# <a name="usage-guidelines"></a>Linee guida per l'utilizzo

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

*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
