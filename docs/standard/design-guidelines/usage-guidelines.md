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
# <a name="usage-guidelines"></a><span data-ttu-id="3ee87-102">Linee guida per l'utilizzo</span><span class="sxs-lookup"><span data-stu-id="3ee87-102">Usage guidelines</span></span>

<span data-ttu-id="3ee87-103">Questa sezione contiene le linee guida per l'uso di tipi comuni in API accessibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="3ee87-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="3ee87-104">Gestisce l'utilizzo diretto dei tipi di Framework predefiniti (ad esempio, gli attributi di serializzazione) e l'overload degli operatori comuni.</span><span class="sxs-lookup"><span data-stu-id="3ee87-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="3ee87-105">L'interfaccia <xref:System.IDisposable?displayProperty=nameWithType> non è descritta in questa sezione, ma è illustrata nella sezione [modello Dispose](../garbage-collection/implementing-dispose.md) .</span><span class="sxs-lookup"><span data-stu-id="3ee87-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="3ee87-106">Per linee guida e informazioni aggiuntive su altri tipi di .NET Framework incorporati comuni, vedere gli argomenti di riferimento per gli argomenti seguenti: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType><xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ee87-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ee87-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3ee87-107">In this section</span></span>

[<span data-ttu-id="3ee87-108">Matrici</span><span class="sxs-lookup"><span data-stu-id="3ee87-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="3ee87-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ee87-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="3ee87-110">raccolte</span><span class="sxs-lookup"><span data-stu-id="3ee87-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="3ee87-111">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="3ee87-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="3ee87-112">Uso di System.Xml</span><span class="sxs-lookup"><span data-stu-id="3ee87-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="3ee87-113">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="3ee87-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="3ee87-114">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3ee87-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="3ee87-115">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3ee87-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ee87-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ee87-116">See also</span></span>

- [<span data-ttu-id="3ee87-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3ee87-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
