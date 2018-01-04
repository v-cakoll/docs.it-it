---
title: Linee guida di utilizzo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3f0a38c69dc286587e702b80ef4093bb98d78b5a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="usage-guidelines"></a><span data-ttu-id="371e3-102">Linee guida di utilizzo</span><span class="sxs-lookup"><span data-stu-id="371e3-102">Usage Guidelines</span></span>
<span data-ttu-id="371e3-103">In questa sezione contiene linee guida per l'utilizzo di tipi comuni nelle API accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="371e3-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="371e3-104">Occupa dell'utilizzo diretto dei tipi (ad esempio, gli attributi di serializzazione) incorporati e overload degli operatori comuni.</span><span class="sxs-lookup"><span data-stu-id="371e3-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="371e3-105">Il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia non viene descritta in questa sezione, ma verrà discusso il [modello Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="371e3-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="371e3-106">Per linee guida e ulteriori informazioni su altri tipi predefiniti di .NET Framework, vedere gli argomenti di riferimento per gli elementi seguenti: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="371e3-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="371e3-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="371e3-107">In This Section</span></span>  
 [<span data-ttu-id="371e3-108">Array</span><span class="sxs-lookup"><span data-stu-id="371e3-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="371e3-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="371e3-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="371e3-110">Raccolte</span><span class="sxs-lookup"><span data-stu-id="371e3-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="371e3-111">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="371e3-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="371e3-112">Uso di System.Xml</span><span class="sxs-lookup"><span data-stu-id="371e3-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="371e3-113">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="371e3-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="371e3-114">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="371e3-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="371e3-115">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="371e3-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371e3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="371e3-116">See Also</span></span>  
 [<span data-ttu-id="371e3-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="371e3-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
