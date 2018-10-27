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
# <a name="usage-guidelines"></a><span data-ttu-id="cc31b-102">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="cc31b-102">Usage guidelines</span></span>

<span data-ttu-id="cc31b-103">In questa sezione contiene le linee guida per l'utilizzo di tipi comuni per le API accessibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="cc31b-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="cc31b-104">Deve gestire con utilizzo diretto di tipi di Framework (ad esempio, gli attributi di serializzazione) e l'overload degli operatori comuni integrati.</span><span class="sxs-lookup"><span data-stu-id="cc31b-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="cc31b-105">Il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia non è coperto in questa sezione, ma verrà discusso il [modello Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="cc31b-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="cc31b-106">Per linee guida e informazioni aggiuntive sulle altre comuni, tipi di .NET Framework incorporati, vedere gli argomenti di riferimento per gli elementi seguenti: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc31b-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cc31b-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cc31b-107">In this section</span></span>

[<span data-ttu-id="cc31b-108">Matrici</span><span class="sxs-lookup"><span data-stu-id="cc31b-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="cc31b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="cc31b-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="cc31b-110">Raccolte</span><span class="sxs-lookup"><span data-stu-id="cc31b-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="cc31b-111">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="cc31b-112">Uso di System.Xml</span><span class="sxs-lookup"><span data-stu-id="cc31b-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="cc31b-113">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="cc31b-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="cc31b-114">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="cc31b-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="cc31b-115">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="cc31b-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc31b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc31b-116">See also</span></span>

- [<span data-ttu-id="cc31b-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="cc31b-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
