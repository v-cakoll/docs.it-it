---
title: Linee guida per l'utilizzo
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 57f6600f60e99c72b72c9f82856dc9eb631a9d4b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708997"
---
# <a name="usage-guidelines"></a>Linee guida per l'utilizzo

Questa sezione contiene le linee guida per l'uso di tipi comuni in API accessibili pubblicamente. Gestisce l'utilizzo diretto dei tipi di Framework predefiniti (ad esempio, gli attributi di serializzazione) e l'overload degli operatori comuni.
  
L'interfaccia <xref:System.IDisposable?displayProperty=nameWithType> non è descritta in questa sezione, ma è illustrata nella sezione [modello Dispose](../garbage-collection/implementing-dispose.md) .

> [!NOTE]
> Per linee guida e informazioni aggiuntive su altri tipi di .NET Framework incorporati comuni, vedere gli argomenti di riferimento per gli argomenti seguenti: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType><xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>In questa sezione

[Matrici](arrays.md)  
[Attributi](attributes.md)  
[raccolte](guidelines-for-collections.md)  
[Serializzazione](serialization.md)  
[Uso di System.Xml](system-xml-usage.md)  
[Operatori di uguaglianza](equality-operators.md)  

*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
