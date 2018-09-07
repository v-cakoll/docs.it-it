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
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44046983"
---
# <a name="static-class-design"></a><span data-ttu-id="8e076-102">Progettazione di classi statiche</span><span class="sxs-lookup"><span data-stu-id="8e076-102">Static Class Design</span></span>
<span data-ttu-id="8e076-103">Una classe statica viene definita come una classe che contiene solo membri statici (naturalmente oltre i membri di istanza ereditati da <xref:System.Object?displayProperty=nameWithType> e possibilmente un costruttore privato).</span><span class="sxs-lookup"><span data-stu-id="8e076-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="8e076-104">Alcuni linguaggi offrono il supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="8e076-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="8e076-105">In c# 2.0 e versioni successive, quando una classe viene dichiarata come statico, è sealed, abstract e non i membri di istanza possono essere sottoposto a override o dichiarati.</span><span class="sxs-lookup"><span data-stu-id="8e076-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="8e076-106">Le classi statiche sono un compromesso tra la progettazione orientata agli oggetti pura e alla semplicità.</span><span class="sxs-lookup"><span data-stu-id="8e076-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="8e076-107">Vengono comunemente usati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari dei metodi di estensione o la funzionalità per il quale un wrapper completa orientata agli oggetti è non autorizzato (ad esempio <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="8e076-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="8e076-108">**✓ DO** usano le classi statiche con cautela.</span><span class="sxs-lookup"><span data-stu-id="8e076-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="8e076-109">Le classi statiche devono essere utilizzate solo come classi di supporto per i core orientate a oggetti di framework.</span><span class="sxs-lookup"><span data-stu-id="8e076-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="8e076-110">**X DO NOT** considerato un bucket varie classi statiche.</span><span class="sxs-lookup"><span data-stu-id="8e076-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="8e076-111">**X DO NOT** dichiarare o eseguire l'override di membri di istanza nelle classi statiche.</span><span class="sxs-lookup"><span data-stu-id="8e076-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="8e076-112">**✓ DO** dichiarare le classi statiche come sealed, abstract, e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone di supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="8e076-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="8e076-113">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8e076-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8e076-114">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8e076-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e076-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e076-115">See also</span></span>

- [<span data-ttu-id="8e076-116">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="8e076-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="8e076-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8e076-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
