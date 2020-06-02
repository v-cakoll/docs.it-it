---
title: Linee guida per l'utilizzo
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 03eaba3e52cb25619f65637efb4f414c22770440
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291344"
---
# <a name="usage-guidelines"></a>Linee guida per l'utilizzo

Questa sezione contiene le linee guida per l'uso di tipi comuni in API accessibili pubblicamente. Gestisce l'utilizzo diretto dei tipi di Framework predefiniti (ad esempio, gli attributi di serializzazione) e l'overload degli operatori comuni.
  
L' <xref:System.IDisposable?displayProperty=nameWithType> interfaccia non è trattata in questa sezione, ma è illustrata nella sezione [modello Dispose](../garbage-collection/implementing-dispose.md) .

> [!NOTE]
> Per linee guida e informazioni aggiuntive su altri tipi di .NET Framework incorporati comuni, vedere gli argomenti di riferimento per gli argomenti seguenti: <xref:System.DateTime?displayProperty=nameWithType> , <xref:System.DateTimeOffset?displayProperty=nameWithType> , <xref:System.ICloneable?displayProperty=nameWithType> , <xref:System.IComparable%601?displayProperty=nameWithType> , <xref:System.IEquatable%601?displayProperty=nameWithType> , <xref:System.Nullable%601?displayProperty=nameWithType> , <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> .

## <a name="in-this-section"></a>Contenuto della sezione

[Matrici](arrays.md)  
[Attributi](attributes.md)  
[raccolte](guidelines-for-collections.md)  
[Serializzazione](serialization.md)  
[Utilizzo di System. XML](system-xml-usage.md)  
[Operatori di uguaglianza](equality-operators.md)  

*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
