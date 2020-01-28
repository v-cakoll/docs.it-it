---
title: Progettazione di classi statiche
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 104fa204a95ef31d34e224348068e3a6505aded5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743602"
---
# <a name="static-class-design"></a><span data-ttu-id="80cea-102">Progettazione di classi statiche</span><span class="sxs-lookup"><span data-stu-id="80cea-102">Static Class Design</span></span>
<span data-ttu-id="80cea-103">Una classe statica viene definita come una classe che contiene solo membri statici, ovviamente oltre ai membri dell'istanza ereditati da <xref:System.Object?displayProperty=nameWithType> e possibilmente da un costruttore privato.</span><span class="sxs-lookup"><span data-stu-id="80cea-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="80cea-104">Alcuni linguaggi forniscono supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="80cea-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="80cea-105">In C# 2,0 e versioni successive, quando una classe viene dichiarata come statica, è sealed, abstract e non è possibile eseguire l'override o la dichiarazione di membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="80cea-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="80cea-106">Le classi statiche costituiscono un compromesso tra la semplicità e la semplicità di progettazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="80cea-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="80cea-107">Sono comunemente usati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari di metodi di estensione o funzionalità per cui un wrapper completo orientato a oggetti non è garantito (ad esempio <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="80cea-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="80cea-108">✔️ utilizzare classi statiche in modo sporadico.</span><span class="sxs-lookup"><span data-stu-id="80cea-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="80cea-109">Le classi statiche devono essere utilizzate solo come classi di supporto per l'elemento principale orientato a oggetti del Framework.</span><span class="sxs-lookup"><span data-stu-id="80cea-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="80cea-110">❌ non considera classi statiche come bucket varie.</span><span class="sxs-lookup"><span data-stu-id="80cea-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="80cea-111">❌ non dichiarare né eseguire l'override dei membri di istanza nelle classi statiche.</span><span class="sxs-lookup"><span data-stu-id="80cea-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="80cea-112">✔️ dichiarare classi statiche come sealed, abstract e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone del supporto incorporato per le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="80cea-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="80cea-113">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="80cea-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="80cea-114">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="80cea-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="80cea-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cea-115">See also</span></span>

- [<span data-ttu-id="80cea-116">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="80cea-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="80cea-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="80cea-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
