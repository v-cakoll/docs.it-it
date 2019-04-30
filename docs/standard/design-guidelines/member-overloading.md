---
title: Overload dei membri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: b13f9e1551aec7e53ba1ac2ed0b9049d46b0a756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945545"
---
# <a name="member-overloading"></a><span data-ttu-id="46457-102">Overload dei membri</span><span class="sxs-lookup"><span data-stu-id="46457-102">Member Overloading</span></span>
<span data-ttu-id="46457-103">Overload dei membri prevede la creazione di due o più membri sullo stesso tipo che si differenziano solo per il numero o il tipo dei parametri, ma hanno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="46457-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="46457-104">Ad esempio, in quanto segue, il `WriteLine` è l'overload di metodo:</span><span class="sxs-lookup"><span data-stu-id="46457-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="46457-105">Poiché solo metodi, costruttori e proprietà indicizzate possono avere parametri, solo i membri possono essere sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="46457-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="46457-106">L'overload è una delle tecniche più importanti per migliorare l'usabilità, la produttività e migliorare la leggibilità delle librerie riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="46457-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="46457-107">L'overload per il numero di parametri rende possibile fornire versioni semplificate di costruttori e metodi.</span><span class="sxs-lookup"><span data-stu-id="46457-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="46457-108">L'overload del tipo di parametro rende possibile usare lo stesso nome di membro per i membri identici operazioni su un set selezionato di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="46457-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="46457-109">**✓ DO** tenta di utilizzare nomi di parametro descrittivi per indicare il valore predefinito utilizzato dagli overload più breve.</span><span class="sxs-lookup"><span data-stu-id="46457-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="46457-110">**X AVOID** arbitrariamente i nomi dei parametri in overload.</span><span class="sxs-lookup"><span data-stu-id="46457-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="46457-111">Se un parametro in uno degli overload rappresenta lo stesso input di un parametro in un altro overload, tali parametri devono avere lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="46457-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="46457-112">**X AVOID** incoerente nell'ordine dei parametri in membri di overload.</span><span class="sxs-lookup"><span data-stu-id="46457-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="46457-113">I parametri con lo stesso nome verrà visualizzato nella stessa posizione in tutti gli overload.</span><span class="sxs-lookup"><span data-stu-id="46457-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="46457-114">**✓ DO** rendere virtuale solo l'overload più lunga (se estendibilità è obbligatoria).</span><span class="sxs-lookup"><span data-stu-id="46457-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="46457-115">Overload più breve deve semplicemente eseguire chiamate a un overload più lungo.</span><span class="sxs-lookup"><span data-stu-id="46457-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="46457-116">**X DO NOT** usare `ref` o `out` modificatori per eseguire l'overload di membri.</span><span class="sxs-lookup"><span data-stu-id="46457-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="46457-117">Alcuni linguaggi non possono risolvere le chiamate agli overload simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="46457-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="46457-118">Inoltre, tali overload in genere hanno una semantica completamente diversa e probabilmente non deve essere overload, ma due metodi distinti invece.</span><span class="sxs-lookup"><span data-stu-id="46457-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="46457-119">**X DO NOT** dispongono di overload con parametri nella stessa posizione e tipi simili ma con una semantica diversa.</span><span class="sxs-lookup"><span data-stu-id="46457-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="46457-120">**✓ DO** consentire `null` da passare per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="46457-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="46457-121">**✓ DO** utilizzare l'overload dei membri anziché definire membri con argomenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="46457-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="46457-122">Gli argomenti predefiniti non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="46457-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="46457-123">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="46457-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="46457-124">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="46457-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46457-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46457-125">See also</span></span>

- [<span data-ttu-id="46457-126">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="46457-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="46457-127">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="46457-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
