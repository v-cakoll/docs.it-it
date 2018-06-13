---
title: Progettazione di classi statiche
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92152600d317c04e3fef26400b11e94a549fde4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571059"
---
# <a name="static-class-design"></a><span data-ttu-id="eab8b-102">Progettazione di classi statiche</span><span class="sxs-lookup"><span data-stu-id="eab8b-102">Static Class Design</span></span>
<span data-ttu-id="eab8b-103">Una classe statica viene definita come una classe che contiene solo membri statici (naturalmente oltre i membri di istanza ereditati dalla <xref:System.Object?displayProperty=nameWithType> e possibilmente un costruttore privato).</span><span class="sxs-lookup"><span data-stu-id="eab8b-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="eab8b-104">Alcuni linguaggi forniscono il supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="eab8b-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="eab8b-105">In c# 2.0 e versioni successive, quando una classe è dichiarata come statico, è astratto sealed e non i membri di istanza possono essere sottoposto a override o dichiarati.</span><span class="sxs-lookup"><span data-stu-id="eab8b-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="eab8b-106">Le classi statiche sono un compromesso tra progettazione orientata agli oggetti pura e alla semplicità.</span><span class="sxs-lookup"><span data-stu-id="eab8b-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="eab8b-107">Comunemente vengono utilizzati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari di metodi di estensione o la funzionalità per i quali è non autorizzato wrapper completa orientata agli oggetti (ad esempio <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="eab8b-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="eab8b-108">**✓ SI** usano le classi statiche con cautela.</span><span class="sxs-lookup"><span data-stu-id="eab8b-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="eab8b-109">Le classi statiche devono essere utilizzate solo come classi di supporto per il framework di base orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="eab8b-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="eab8b-110">**X non** considerato un bucket varie classi statiche.</span><span class="sxs-lookup"><span data-stu-id="eab8b-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="eab8b-111">**X non** dichiarare o eseguire l'override di membri di istanza nelle classi statiche.</span><span class="sxs-lookup"><span data-stu-id="eab8b-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="eab8b-112">**✓ SI** dichiarare le classi statiche come sealed, abstract, e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone di supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="eab8b-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="eab8b-113">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="eab8b-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="eab8b-114">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="eab8b-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab8b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eab8b-115">See Also</span></span>  
 [<span data-ttu-id="eab8b-116">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="eab8b-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="eab8b-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="eab8b-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
